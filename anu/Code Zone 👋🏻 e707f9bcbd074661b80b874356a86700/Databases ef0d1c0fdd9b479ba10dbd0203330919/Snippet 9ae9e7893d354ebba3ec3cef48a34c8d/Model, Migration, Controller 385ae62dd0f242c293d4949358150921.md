# Model, Migration, Controller

Chapter: Basic Laravel
No.: 2
Type: framework, laravel

> Pretty command
> 

```php
php artisan make:model -mrc NameProject
```

> basic command
> 

```php
php artisan make:migration nama

php artisan make:controller namaController —resource

php artisan make:model namaModel
```

> model
> 

```php
<?php

use Illuminate\Database\Migrations\Migration;
use Illuminate\Database\Schema\Blueprint;
use Illuminate\Support\Facades\Schema;

return new class extends Migration
{
    public function up()
    {
        Schema::create('students', function (Blueprint $table) {
            $table->id();
            //tambahkan kode berikut
            $table->string('name');
            $table->string('kelas');
            //tambahkan kode di atas
            $table->timestamps();
        });
    }

    public function down()
    {
        Schema::dropIfExists('students');
    }
};
```

[https://laravel.com/docs/9.x/migrations#available-column-types](https://laravel.com/docs/9.x/migrations#available-column-types)

```php
php artisan migrate:fresh
```

> route
> 

```php
Route::get($uri, $callback);
Route::post($uri, $callback);
Route::put($uri, $callback);
Route::patch($uri, $callback);
Route::delete($uri, $callback);
Route::options($uri, $callback);

Route::resource($uri, $callback); // get 7 function get, put, delete etc
```

[https://laravel.com/docs/9.x/routing#available-router-methods](https://laravel.com/docs/9.x/routing#available-router-methods)

example

```php
Route::resource('murid', MuridController::class);
```

> controller
>