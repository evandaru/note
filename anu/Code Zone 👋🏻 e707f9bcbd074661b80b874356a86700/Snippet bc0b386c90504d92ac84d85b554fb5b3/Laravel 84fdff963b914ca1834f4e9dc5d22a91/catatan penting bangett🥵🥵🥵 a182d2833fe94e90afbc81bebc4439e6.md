# catatan penting bangett🥵🥵🥵

# untuk membuat auth

passwordnya harus pake `hash` ato ke enskripsi

perlu diperhatikan di bag `model`

```php
<?php
namespace App\Models;

use Illuminate\Database\Eloquent\Factories\HasFactory;
use Illuminate\Foundation\Auth\User as Authenticatable;

class login extends Authenticatable
{
	use HasFactory;
}
```

```php
<?php

namespace App\Models;

use Illuminate\Database\Eloquent\Factories\HasFactory;
use Illuminate\Database\Eloquent\Model;

class login extends Model
{
	use HasFactory;
}
```

# trus jangan lupa

setting di `config/auth`

```php
'providers' => [
        'users' => [
            'driver' => 'eloquent',
            'model' => App\Models\diganti seseuai nama model::class,
        ],
```

# multi authh paling simpel pakde 🥵

```php
public function login(Request $request)
    {
        //validate
        // $request->validate([
        //     'email' => 'required',
        //     'password' => 'required'
        // ]);
        $inpologin = [
            'username' => $request->username,
            'password' => $request->password,
        ];
        if (Auth::attempt($inpologin)) {
            if (Auth()->user()->username === 'fauzan') {
                return 'anda admin';
            }
            return view('user');
        }
        return view('login');
    }
```

# membuat `hash`di password

```php
public function register(Request $request)
    {
        $data = [
            'nama' => $request->nama,
            'email' => $request->email,
            'jenis_kelamin' => $request->jenis_kelamin,
            'password' => Hash::make($request->password),
        ];

        login::create($data);
        return redirect('/login');
    }
```

# membuat seeder dan melakukannya

```php
php artisan make:seed NameOfSeeder
```

```php
php artisan db:seed --class=UsersTableSeeder
```

```php
public function run()
    {
        DB::table('ikans')->insert([
            [
                'nama' => 'piranha',
                'skill' => 'renang',
                'jk' => 'gk ada',
            ],
		}
```

# membuat pagination

di controller

```php
$ikan = ikan::paginate(5);
        return view('show', compact('ikan'));
```

di vienya

```php
@foreach ($ikan as $index => $ikans)
     
...
@endforeach

...

{{ $ikan->links() }}
```

di AppServiceProvider

```php
//inget rawan error
use Illuminate\Pagination\Paginator;
public function boot()
    {
        Paginator::useBootstrap();
    }

```

biar angkanya bisa nambah setiap ganti anu😭

```php
@foreach ($ikan as $index => $ikans)
                    <tr>
                        <th scope="row">{{ $index + $ikan->firstItem() }}.</th>
                        <td>{{ $ikans->nama }}</td>
                        <td>{{ $ikans->skill }}</td>
                        <td>{{ $ikans->jk }}</td>
                    </tr>
                @endforeach
```

# search gampang

di controllernya

```php
public function index(Request $request)
    {
        if ($request->has('search')) {
            $murid = Murid::where('nama', 'LIKE', '%' . $request->search . '%')->paginate(5);
        } else {
            $murid = Murid::paginate(5);
        };
        return view('tables', compact('murid'));
    }
```

di viewnya

```html
<form action="/dashboard" method="GET">
<input class="form-control" placeholder="Cari Nama peserta" type="search" name="search">
</form>
```

# Export sql ke excel

```html
composer require maatwebsite/excel
```

**config/app.php**

```html
'providers' => [
    /*
	     * Package Service Providers...
     */
    Maatwebsite\Excel\ExcelServiceProvider::class,
]

//itu pun juga

'aliases' => [
    ...
    'Excel' => Maatwebsite\Excel\Facades\Excel::class,
]
```

```html
php artisan vendor:publish --provider="Maatwebsite\Excel\ExcelServiceProvider" --tag=config
```

# membuat checkbox

di controllernya fokus sama `implode()` 

```php
public function input(Request $request)
    {
        $skill = implode(",", $request->skill);
        $data = [
            'nama' => $request->nama,
            'skill' => $skill,
            'jk' => $request->jk,
        ];
        ikan::create($data);
        return 'berhasil';
    }
```

trus di `name=”ikan[]”` nya jangan lupa dikasih `array[]`

```php
<div class="form-check">
                <input class="form-check-input" name="skill[]" type="checkbox" value="renang" id="flexCheckDefault">
                <label class="form-check-label" for="flexCheckDefault">
                    Renang
                </label>
            </div>
```

# Make validation number in laravel

```jsx
$no_wa = implode($request->validate(['no_wa' => 'required|digits:12']));

if (!$request->validate(['no_wa' => 'required|digits:12'])) {
            return redirect()->back()->withErrors([
                'no_wa' => 'no anda kurang tepat.',
            ]);
        }

//nnti tinggal panggil oawkoawko😂
```

# error handling

```jsx
Illuminate\Database\QueryException 

  SQLSTATE[42000]: Syntax error or access violation: 1115 Unknown character set: 'utf8mb4' (SQL: select * from information_schema.tables where table_schema = laravel and table_name = migrations and table_type = 'BASE TABLE')

  at D:\laragon2\www\belajar2\vendor\laravel\framework\src\Illuminate\Database\Connection.php:760
    756▕         // If an exception occurs when attempting to run a query, we'll format the error
    757▕         // message to include the bindings with SQL, which will make this exception a
    758▕         // lot more helpful to the developer instead of just the database's errors.
    759▕         catch (Exception $e) {
  ➜ 760▕             throw new QueryException(
    761▕                 $query, $this->prepareBindings($bindings), $e
    762▕             );
    763▕         }
    764▕     }

  1   D:\laragon2\www\belajar2\vendor\laravel\framework\src\Illuminate\Database\Connectors\MySqlConnector.php:76
      PDOException::("SQLSTATE[42000]: Syntax error or access violation: 1115 Unknown character set: 'utf8mb4'")

  2   D:\laragon2\www\belajar2\vendor\laravel\framework\src\Illuminate\Database\Connectors\MySqlConnector.php:76
      PDO::prepare("set names 'utf8mb4' collate 'utf8mb4_unicode_ci'")
```

solution

`config\database.php`

```jsx
'mysql' => [
...
            'charset' => 'utf8mb4',
            'collation' => 'utf8mb4_unicode_ci',
...
        ],
```

to

```jsx
'mysql' => [
...
            'charset' => 'utf8',
            'collation' => 'utf8_unicode_ci',
...
        ],
```

[http://sujanadoang.blogspot.com/2018/03/solved-illuminatedatabasequeryexception.html](http://sujanadoang.blogspot.com/2018/03/solved-illuminatedatabasequeryexception.html)