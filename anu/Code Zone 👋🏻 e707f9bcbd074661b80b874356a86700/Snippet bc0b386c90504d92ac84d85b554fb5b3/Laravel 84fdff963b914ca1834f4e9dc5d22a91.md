# Laravel

Programing Languange: PHP
Status Learn: In progress
type: framework

# Laravel snipet

[Untitled Database](Laravel%2084fdff963b914ca1834f4e9dc5d22a91/Untitled%20Database%20b8db284803aa461f8659dc5ffe242fe8.csv)

> Link learning
> 

[Laravel Bootcamp - Learn the PHP Framework for Web Artisans](https://bootcamp.laravel.com/blade/creating-chirps)

- draft
    
    # penting coyy
    
    ### how to clone github file
    
    make file .env → terus di isi sepelunya
    
    ```php
    composer install
    ```
    
    buat key value
    
    ```php
    php artisan key:generate
    ```
    
    buat jalanin apps nya ngab😱
    
    ```php
    php artisan serve
    ```
    
    - intro laravel
        
        😭perkenalan 
        
        😭instalasi
        
        😭configuration
        
    - struktur laravel
        
        ![Untitled](Laravel%2084fdff963b914ca1834f4e9dc5d22a91/Untitled.png)
        
        # Router
        
        dalamnya buat buat alamat linknya
        
        ```php
        Route::get('/', function () {
            return view('welcome');
        });
        ```
        
        # View
        
        ini buat bikin tampilan awal 
        
        `resources\views`
        
        ```php
        @include('partials.font') //buat ngambil 
        
        @yield('container') //anggep export
        @section('container') //enggep impot
        
        @extends('layout.master')
        ```
        
    - CRUD LARAVEL
    - 
    
    tahapan main laravel
    
    1. membuat migration
    `php artisan make:migration nama`
    2. membuat controller
    `php artisan make:controller namaController —resource`
    3. membuat model
    `php artisan make:model namaModel`
    
    simple syntax
    
    ```php
    php artisan make:model -mrc Chirp
    ```
    

# `php artisan make:model -mrc namaItu`

# Mini Snippet CROOOOOT💦💦💦

<aside>
🥎 **create**

fokus di `controller` yg `store`

```php
public function store(Request $request)
    {
        $data = [
            'nama_buku' => $request->nama_buku,
            'penerbit_buku' => $request->penerbit_buku,
            'pengarang_buku' => $request->pengarang_buku,
            'isbn' => $request->isbn,
        ];
        buku::create($data);
        return "aku suka ikannnn😎😎😎😎";
    }
```

fokus di `model` membuat `$fillabel`  ato `$guarded`

```php
protected $fillable = [
//nama fillnya
	'nama',
	'skill',
]

//ato gini (lawan nya si $fillable)

protected $guarded = [];
```

[https://laravel.com/docs/9.x/eloquent#inserts](https://laravel.com/docs/9.x/eloquent#inserts)

fokus di `view` link buat redirect ke nama file itu sendiri `{{ url(’coba’) }}`

</aside>

# make a form

> klo ada error
> 

```php
@error('nama :namenya:')
    
@enderror
```

[catatan penting bangett🥵🥵🥵](Laravel%2084fdff963b914ca1834f4e9dc5d22a91/catatan%20penting%20bangett%F0%9F%A5%B5%F0%9F%A5%B5%F0%9F%A5%B5%20a182d2833fe94e90afbc81bebc4439e6.md)