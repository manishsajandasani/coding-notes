# Prerequisite Knowledge to Learn Laravel

- PHP (Strong OOP Knowledge)
- MySQL

# What is Laravel

- Free and Open-Source PHP Framework
- MVC Based Architectural Pattern 
- Developed by Taylor Otwell - June 2011
- Uses
    - Create Web Apps
    - Create APIs

# What is MVC Pattern

- M : Model (DATABASE)
- V : View (HTML) 
- C : Controller (BUSINESS LOGIC : MEDIATOR BETWEEN MODEL AND VIEW)
- Works on 2 Principles
    - Separation of Concerns
    - Code Organization 
- Work Flow
    - User ----- request ----- Controller 
    - Controller ----- request data ----- Model
    - Model ----- response data ----- Controller
    - Controller ----- send data ----- View 
    - View ----- response ----- User
- Benfits
    - Organized Code
    - Independent Block
    - Reduces the complexity of Web Applications
    - Easy to Maintain
    - Easy to Modify
    - Improved Collaboration
    - Code Reusability 
    - Platform Independence 
- Popular MVC Frameworks
    - Laravel
    - Symphony
    - CodeIgniter
    - Yii
    - CakePHP
    - Zend Framework

# What is Framework?

- Programming frameworks are sets of pre-written-code and libraries that provide a foundation for developing software applications. 
- Pre-written Code & Library
    - Tools
    - Components 
        - Database
        - Caching
        - Pagination
        - Session Management
        - Form Handling
        - Security Mechanisms
        - User Authentication
        - APIs
        - Payment Gateways
    - Modules
- Benefits 
    - Code Organization
    - Reusability
    - Standardization
    - Testing and Debugging Support
    - Community and Support 

# Benefits of Laravel Framework

- Open Source
- Elegant Syntax
- MVC Architecture
- Database Migration and ORM
- Robust Routing System 
- Command Line Interface (Composer)
- Powerful Template Engine (Blade Template)
- Authentication and Authorization
- Testing and Debugging
- Security (XSS, CSRF, SQL Injection)
- Scalability and Performance (Redis and Memcached)
- Robust Ecosystem and Community   

# Learn

- Artisan CLI
- Routing
- Views
- Blade Template
- Controllers
- Model
- Database
- Eloquent ORM
- Migration
- Middleware
- Form Validation
- Authentication
- Handling File Upload
- APIs Validation
- CRUD Project 
- News Blog Project 
- CRUD with AJAX
- Facades
- Faker
- Notifications
- Etc. 

# Install XAMPP and Composer

- Install XAMPP (PHP 10.1 & MySQL)
- Install Composer
- Install Laravel 
- Install VS Code Editor 

# What is Composer?

- A Dependency Manager for PHP
- Install Package with Single Command
- Can update version package, framework etc. 
- Composer can be used with any PHP framework 

# Important Links to Resolve Errors

- https://stackoverflow.com/questions/2643502/git-how-to-solve-permission-denied-publickey-error-when-using-git
- https://laravel.com/docs/10.x/migrations#column-method-string

# My Doubts
    - How to add a new column in a table without deleting existing data
    - How to udpate column's name in an existing table 

# Commands

```console
php -v
composer -v
composer
echo %PATH%
composer global require laravel/installer
laravel new example-app
composer create-project laravel/laravel example-app
php artisan
php artisan serve

<!-- Routing Related Artisan Commands -->
php artisan route -h
php artisan route:list
php artisan route:list --except-vendor
php artisan route:list --path=post

php artisan help
php artisan help make:controller

php artisan make:controller PageController
php artisan make:controller TestController --invokable
php artisan make:controller TestController --i

php artisan make:migration create_students_table

php artisan migrate
php artisan migrate:status
php artisan migrate --force
php artisan migrate:rollback   (undo our last migration)
php artisan migrate:rollback --step=3   (undo our last 3 migrations)
php artisan migrate:rollback --batch=3   (undo the 3rd migration)
php artisan migrate:reset   (it removes all tables from database except one 'migrations')
php artisan migrate:refresh   (it rollbacks and runs migrations)
php artisan migrate:fresh   (it drops all tables and runs migrations)
php artisan make:model Task -m   (it creates model with its migration file)
php artisan make:migration add_percentage_column_to_students_table --table=students  (adds new column in students table)
```

# Short Code Snippets

```console
Laravel v{{ Illuminate\Foundation\Application::VERSION }} (PHP v{{ PHP_VERSION }})
```

# Use SCSS in Laravel (With Vite)

```console
npm install
npm add -D sass
npm run dev
npm run build
```

# VS Code Extensions

- PHP Intelephense
- PHP Namespace Resolver
- Laravel Extra Intellisence
- Laravel Blade
- Laravel Blade Snippets
- Laravel goto View

# Project Folder & File Structure

- Model Folder (Database / SQL Queries Handling Files)
- Controller Folder (Business Logic Files)
- View Folder (HTML Files)
- Routing Folder (URL Defining Files)
- Assets (Public) Folder (Images / Fonts / Videos / CSS / JS / Document Files)
- Config Folder (Configuration Files)
- Storage Folder (Log Files for Caching)
- Tests Folder (Unit Testing Files)
- Vendor Folder (Contains all Downloaded Packages)

# Basic Routing

- Route means URL (Webpage URL and APIs URL)
- Pure PHP URL
    - http://localhost/about.php
    - http://localhost/pages/about.php
- Laravel URL
    - http://localhost/about
- Have to define routes in **routes/web.php**

# Route Parameters with Route Constraints

```console
http://localhost/post/50
http://localhost/post/skillnative
http://localhost/post/users10
http://localhost/post/@users10
http://localhost/post/$users10
http://localhost/post/_users10

Route::get("/post/{id}", function (int $id) {
    return "<h1>ID is {$id} </h1>";
});

Route::get("/post/{name}", function (string $name) {
    return "<h1>Name is {$name} </h1>";
});

Route::get("/post/{id?}", function (int $id = null) {
    return "<h1>ID is {$id} </h1>";
});

Route::get("/post/{id?}", function (int $id = null) {
    if ($id) {
        return "<h1> ID is {$id} </h1>";
    } else {
        return "<h1> No ID Found </h1>";
    }
});

Route::get("/post/{id?}/comment/{commentId?}", function ($id = null, $commentId = null) {
    if ($id) {
        return "<h1> ID is {$id} </h1> <h2> Comment ID is {$commentId} </h2>";
    } else {
        return "<h1> No ID Found </h1>";
    }
});

<!-- Route Constraints -->
http://localhost/post/50 ==================> whereNumber('id')
http://localhost/post/skillnative ==================> whereAlpha('name')
http://localhost/post/users10 ==================> whereAlphaNumeric('name')
http://localhost/post/song ==================> whereIn('category', ['movie', 'song'])
http://localhost/post/@10 ==================> (Regular Expression) where('id', '[@0-9]+')

Route::get("/url-1/{value?}", function ($value = null) {
    return "<h1> {$value} </h1>";
})->whereNumber('value');

Route::get("/url-2/{value?}", function ($value = null) {
    return "<h1> {$value} </h1>";
})->whereAlpha('value');

Route::get("/url-3/{value?}", function ($value = null) {
    return "<h1> {$value} </h1>";
})->whereAlphaNumeric('value');

Route::get("/url-4/{value?}", function ($value = null) {
    return "<h1> {$value} </h1>";
})->whereIn('value', ['Manish', 'Sanjay']);

Route::get("/url-5/{value?}", function ($value = null) {
    return "<h1> {$value} </h1>";
})->where('value', '[@0-9]+');

Route::get("/url-6/{value?}", function ($value = null) {
    return "<h1> {$value} </h1>";
})->where('value', '[@0-9a-zA-Z]+');

Route::get("/url-7/{id}/comment/{commentId}", function ($id, $commentId) {
    return "<h1 style='margin-bottom: 0'> ID is {$id} </h1> 
            <h2 style='margin-top: 0'> Comment ID is {$commentId} </h2>";
})->whereNumber('id')->whereAlpha('commentId');
```

# Named Routes

- Problem
```console
Route::get("/page/about", function () {
    return "About Page";
});

first.blade.php
<a href="/page/about">About</a>

second.blade.php
<a href="/page/about">About</a>

third.blade.php
<a href="/page/about">About</a>

Now, if we were to change the route from /page/about to /page/about-us, then we would have to change it in all three blade files.
Instead, we could use Laravel Named Route.

Route::get("/page/about", function () {
    return "About Page";
})->name('about');    (here we added named routed and we call it 'about')

first.blade.php
<a href="{{ route('about') }}">About</a>

second.blade.php
<a href="{{ route('about') }}">About</a>

third.blade.php
<a href="{{ route('about') }}">About</a>
```

- Example
```console
==> web.php
Route::get("/about-us", function () {
    return "<h1> About Page </h1>";
})->name("about");

Route::view("/first", 'first');
Route::view("/second", 'second');
Route::view("/third", 'third');

==> first, second, and third.blade.php
<h1>
    <a href="{{ route('about') }}">
        About Page
    </a>
</h1>
```

# Redirect  
- Learn about Redirection Codes
- https://en.wikipedia.org/wiki/URL_redirection
```console
==> web.php 
Route::redirect("/fourth", '/third');
Route::redirect("/fourth", '/third', 301);
```

# Route Groups

```console
==> welcome.php
<ul>
    <li>
        <a href="{{ route('page.home') }}"> Page Home </a>
    </li>
    <li>
        <a href="{{ route('page.about') }}">Page About </a>
    </li>
    <li>
        <a href="{{ route('page.contact') }}">Page Contact </a>
    </li>
</ul>

==> web.php
Route::prefix("page")->group(function () {
    Route::get("/home", function () {
        return "<h1> Page : Home </h1>";
    })->name("page.home");
    Route::get("/about", function () {
        return "<h1> Page : About </h1>";
    })->name("page.about");
    Route::get("/contact", function () {
        return "<h1> Page : Contact </h1>";
    })->name("page.contact");
});
```

# Fallback (404 Page Not Found)
```console
==> web.php 
Route::fallback(function () {
    return "<h1> Page Not Found </h1>";
});
```

# Blade Template

- Template Engine based on PHP
- Blade provides a clean and convenient way to create views in Laravel
- Helps to create dynamic and reusable templates
- Has HTML and PHP
- Prevents cross-site-scripting (XSS) Attacks

```console
<?php echo "Hello"; ?>                      => Blade: {{ "Hello" }}
<?php echo $name; ?>                        => Blade: {{ $name }}
<?php echo "<h1> Hello </h1>"; ?>           => Blade: {!! "<h1> Hello </h1>" !!}
<?php echo "<script> ..... </script>"; ?>   => Blade: {!! "<script> ..... </script>" !!}

<?php
    ....                            
?>
In Blade:
@php
    ....
@endphp

<?php
    // Comment                            
?>
In Blade: 
{{-- Comment --}}

@if(condition)
// Statement
@elseif(condition)
// Statement
@else
// Statement
@endif

@switch($i)
    @case(1)
        // First Case...
        @break 
    @case(2)
        // Second Case...
        @break 
    @default
        // Default Case...
@endswitch

@isset($records)
....
@endisset

@empty($records)
....
@endempty

@for($i=0; $i<10; $i++>)
....
@endfor

@foreach($users as $user)
....
@endforeach

@while(condition)
....
@endwhile

@forelse($users as $user)
<li> {{ $user->name }} </li>
@empty
<p> No Users </p>
@endforelse

@continue
@break

========= Examples =========
{{ 5 + 2 }}

<br>

{{ "Hello World" }}

<br>

{{ "<h1>Hello World</h1>" }}

<br>

{!! "<h1>Hello World</h1>" !!}

<br>

{!! '
<script>console.log("Console Me");</script>
' !!}

{{-- This is Blade Comment --}}

@php
$user = "Manish";
$names = ["Ramesh", "Suresh", "Pravesh", "Naresh"];
$users = (array)[
(object)["name" => "Manish", "age" => 31],
(object)["name" => "Kailash", "age" => 32],
(object)["name" => "Sanjay", "age" => 33],
(object)["name" => "Geet", "age" => 34],
];
@endphp

{{ $user }}
@{{ $user }}

<ul>
    @foreach($names as $name)
    <li>{{ $name }}</li>
    @endforeach
</ul>

<ul>
    @foreach($users as $user)
    <li>Name is {{ $user->name }} & Age is {{ $user->age }}</li>
    @endforeach
</ul>

@if(false)
{{ "This is True" }}
@else
{{ "This is False" }}
@endif

@@if(True)
```

# Loop Variables for @foreach

```console
$loop->index
$loop->iteration
$loop->remaining
$loop->count
$loop->first
$loop->last
$loop->even
$loop->odd
$loop->depth
$loop->parent

========= Examples =========
<ul>
    @foreach($users as $user)
    <li>{{ $loop->index }} : Name is {{ $user->name }} & Age is {{ $user->age }}</li>
    @endforeach
</ul>

<ul>
    @foreach($users as $user)
    <li>{{ $loop->count }} : Name is {{ $user->name }} & Age is {{ $user->age }}</li>
    @endforeach
</ul>

<ul>
    @foreach($users as $user)
    <li>{{ $loop->iteration }} : Name is {{ $user->name }} & Age is {{ $user->age }}</li>
    @endforeach
</ul>

<ul>
    @foreach($users as $user)
    @if($loop->first)
    <li style="color: green;">Name is {{ $user->name }} & Age is {{ $user->age }}</li>
    @else
    <li>Name is {{ $user->name }} & Age is {{ $user->age }}</li>
    @endif
    @endforeach
</ul>

<ul>
    @foreach($users as $user)
    @if($loop->last)
    <li style="color: red;">Name is {{ $user->name }} & Age is {{ $user->age }}</li>
    @else
    <li>Name is {{ $user->name }} & Age is {{ $user->age }}</li>
    @endif
    @endforeach
</ul>

<ul>
    @foreach($users as $user)
    @if($loop->odd)
    <li style="color: orange;">Name is {{ $user->name }} & Age is {{ $user->age }}</li>
    @else
    <li>Name is {{ $user->name }} & Age is {{ $user->age }}</li>
    @endif
    @endforeach
</ul>
```

# Subviews (Blade Template Main Directives)

- @include
- @section
- @extend
- @yield

```console
========= @include, @includeIf, @includeWhen, @includeUnless Examples =========
==> welcome.blade.php
@php
$users = (array)[
(object)["name" => "Manish", "city" => "Bhopal"],
(object)["name" => "Satish", "city" => "Indore"],
(object)["name" => "Raveesh", "city" => "Sehore"],
];

$contacts = [7745991848, 7828783727, 8827991222];
$showContacts = "";
$showAbout = false;
@endphp

@include("pages.header", ["users" => $users])
<h1>Welcome Page </h1>
@include("pages.footer")
@includeIf("pages.component")
@includeWhen(empty($showContacts), "pages.contact", ["contacts", $contacts])
@includeUnless($showAbout, "pages.about")

==> pages/header.blade.php
<h1>Header</h1>
<h2 style="margin-bottom: 0;">Users List</h2>

@forelse($users as $user)
<p style="margin: 0;">{{ $user->name }}</p>
@empty
<p style="margin: 0;">No Users Data</p>
@endforelse

==> pages/footer.blade.php
<h1>Footer</h1>

==> pages/contact.blade.php
<h1 style="margin-bottom: 0;">Contacts List</h1>

@forelse($contacts as $contact)
<p style="margin: 0;">{{ $contact }}</p>
@empty
<p style="margin: 0;">No contacts Data</p>
@endforelse

==> pages/about.blade.php
<h1>About Page</h1>
```

# Blade Template Inheritance

```console
==> web.php
Route::get('/', function () {
    return view('welcome');
});

Route::get("/home", function () {
    return view("pages.home");
})->name("homepage");

Route::get("/about", function () {
    return view("pages.about");
})->name("aboutpage");

Route::get("/contact", function () {
    return view("pages.contact");
})->name("contactpage");

==> welcome.blade.php
<ul>
    <li>
        <a href="{{ route('homepage') }}">Home</a>
    </li>
    <li>
        <a href="{{ route('aboutpage') }}">About</a>
    </li>
    <li>
        <a href="{{ route('contactpage') }}">Contact</a>
    </li>
</ul>

==> layout.blade.php
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Skillnative - @yield('title', 'Website')</title>

    <link rel="stylesheet" href="{{ asset('css/styles.css') }}">
</head>
<body>
    <h1>Header</h1>

    @hasSection("content")
    @yield("content")
    @else
    <h1>No Content Found</h1>
    @endif

    @section("sidebar")
    <ul>
        <li>Home</li>
        <li>Careers</li>
        <li>Contact</li>
    </ul>
    @show

    <h1>Footer</h1>
</body>
</html>

==> home.blade.php
@extends("layout")

@section('title')
Home Page
@endsection

@section('content')
<h2>Home Page</h2>
@endsection

==> about.blade.php
@extends("layout")
@section('content')
<h2>About Page</h2>
@endsection

==> contact.blade.php
@extends("layout")
@section('content')

@endsection

@section('sidebar')
@parent
<p>This is contact page sidebar</p>
@endsection
```    

# PHP in JavaScript

```console
@php
$title = "SkillNative";
$letters = ["A", "B", "C", "D"];
$city = "Sehore";
@endphp

<script>
    console.log(@json($title));

    let names = @json($letters);
    names.forEach(element => {
        console.log(element);
    });

    let city = {{ Js::from($city) }};
    console.log(city);
</script>
```

# JS in Template Inheritance

- Difference between @section and @push is @push allows you to place same code multiple times at multiple places in the extended file.
- Can call @push multiple times here and there. 

```console
==> layout.blade.php
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Skillnative - @yield('title', 'Website')</title>

    <link rel="stylesheet" href="{{ asset('css/styles.css') }}">

    @stack('style')
</head>

<body>
    <h1>Header</h1>

    @hasSection("content")
    @yield("content")
    @else
    <h1>No Content Found</h1>
    @endif

    @section("sidebar")
    <ul>
        <li>Home</li>
        <li>Careers</li>
        <li>Contact</li>
    </ul>
    @show

    <h1>Footer</h1>

    @stack('scripts')
</body>

</html>

==> home.blade.php
@extends("layout")

@push('style')
<style>
    body {
        background: lightgreen;
    }
</style>
@endpush

@prepend('style')
<style>
    body {
        font-family: cursive;
    }
</style>
@endprepend

@section('title')
Home Page 456
@endsection

@section('content')
<h2>Home Page</h2>
@endsection

@verbatim
<div id="app">{{ message }}</div>
@endverbatim

@push('scripts')
<script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>
<script>
    const { createApp, ref } = Vue

    createApp({
        setup() {
            const message = ref('Hello vue!')
            return {
                message
            }
        }
    }).mount('#app')
</script>
@endpush

==> about.blade.php
@extends('layout')

@section('content')
<h2>About Page</h2>
@endsection

==> contact.blade.php
@extends("layout")

@section('content')

@endsection

@section('sidebar')
@parent
<p>This is contact page sidebar</p>
@endsection
```

# Passing Data : From Route To View

```console
==> web.php
function getUsers()
{
    return [
        1 => ["name" => "Manish", "phone" => 7745991848, "city" => "Bhopal"],
        2 => ["name" => "Sanjay", "phone" => 7828783727, "city" => "Sehore"],
        3 => ["name" => "Kailash", "phone" => 8827991222, "city" => "Mandideep"],
        4 => ["name" => "Chiku", "phone" => 7788994455, "city" => "Panchmarhi"]
    ];
}

Route::get('/', function () {
    $user = "Manish";
    $hobbies = ["Reading", "Learning", "Training"];
    $printJS = "<script> console.log('Print JS'); </script>";
    $city = "Sehore";
    $names = getUsers();

    // return view('welcome', ["user" => $user, "hobbies" => $hobbies, "printJS" => $printJS]);
    // return view('welcome')->with("user", $user)->with("hobbies", $hobbies)->with("printJS", $printJS);
    return view('welcome')->withUser($user)->withHobbies($hobbies)->withPrintJS($printJS)->withCity($city)->withNames($names);
});

Route::get("user/{id}", function ($id) {
    abort_if(!isset(getUsers()[$id]), 404);
    return getUsers()[$id];
})->name("user.view");

==> welcome.blade.php
<h1>
    Username is {{ $user }}
</h1>

<ul>
    @foreach($hobbies as $hobby)
    <li>{{ $hobby }}</li>
    @endforeach
</ul>

<p>
    {{ $printJS }}
</p>

<p>
    {!! $printJS !!}
</p>

<p>
    City = {{ !empty($city) ? $city : "No City" }}
</p>

<table border="2" cellpadding="10">
    @foreach($names as $id => $name)
    <tr>
        <td>{{ $name["name"] }}</td>
        <td>{{ $name["phone"] }}</td>
        <td>{{ $name["city"] }}</td>
        <td>
            <a href="{{ route('user.view', $id) }}">
                Show
            </a>
        </td>
    </tr>
    @endforeach
</table>
```

# Controllers, Controllers Groups, Single Action Controllers

- Must know PHP OOPS
- Create Controller File  [php artisan make:controller UserController]
- Create Controller Class
- Create Route

```console
==> web.php
Route::get("/", function () {
    return view("welcome");
});
Route::controller(PageController::class)->group(function () {
    Route::prefix("pages/")->name('pages.')->group(function () {
        Route::get("/home", "index")->name('home');
        Route::get("/users/{id?}", "users")->whereNumber('id')->name('users');
    });
});
Route::get("/invokable", InvokableController::class);

==> PageController.php
<?php
namespace App\Http\Controllers;
use Illuminate\Http\Request;
class PageController extends Controller
{
    public function index()
    {
        return view("pages.home");
    }

    public function users(string $id = null)
    {
        // return view("pages.users", ["id" => $id]);
        return view("pages.users", compact('id'));
    }
}

==> InvokableController.php
<?php
namespace App\Http\Controllers;
use Illuminate\Http\Request;
class InvokableController extends Controller
{
    /**
     * Handle the incoming request.
     */
    public function __invoke(Request $request)
    {
        return view("pages.invoke");
    }
}

==> welcome.blade.php3
<ul>
    <li> <a href="{{ route('pages.home') }}">Home</a> </li>
    <li> <a href="{{ route('pages.users') }}">Users</a> </li>
</ul>

==> home.blade.php
<h1> Home Page </h1>

==> users.blade.php
<h1> Users Page </h1>
<h2> ID is {{ $id }} </h2>

==> invoke.blade.php
<h1> Invoke View File </h1>
```

# Database Migration

- Laravel DataTypes 
    - https://laravel.com/docs/10.x/migrations#column-method-string
- Steps to Work in Model
    - Create Database
        - Manually: CREATE DATABASE laravel-db (or)
        - Xampp (Phpmyadmin)
    - Database Settings in your Laravel Project
        - ProjectFolder/.env (uses ProjectFolder/config/database.php)    
    - Create Database Migration (Create tables in database)
        - php artisan make:migration create_students_table
        - ProjectFolder/database/migrations/2023_07_02_112651_create_students_table.php 
        - php artisan migrate
    - Seeding
    - Create Model

# Modifications with Migration

- Column Modifications
    - Add New Column
    - Rename Column
    - Delete Column
    - Change Column Order
    - Change DataType or Size of Column
- Table Modifications
    - Rename Table
    - Delete Table
- In order to peform modifications to a table perform these 3 steps:
    - First create a migration with the table name flag
    - In the migration file, do the changes
    - run php artisan migrate command
- Always Remember
    - Give plural name to a table
    - when you run migrate command the up methods runs 
    - when you run migrate:rollback command the down method runs
- To rename a column
    - $table->renameColumn('from', 'to')   
    - The above command is new in laravel 10. works with MySQL > 8.0.3 and MariaDB > 10.5.2. In order to run it install doctrine/dbal via composer [composer require doctrine/dbal]
- To delete a column
    - $table->dropColumn('city')
    - $table->dropColumn(['city','age','gender'])
- To update the size of a column
    - $table->string('city', 100)->change() 
    - $table->integer('votes')->unsigned()->default(1)->comment('my comment')->change() 
- To change column order
```console
$table->after('password', function(Blueprint $table) {
    $table->string('address', 100); 
    $table->string('city', 100); 
})    
```
- Modify table with migration
    - $table->rename('from', 'to');
    - $table->drop('users');
    - Schema::dropIfExists('users');
```console
if(Schema::hasTable('students')) {
    // Does students table exist?
}
if(Schema::hasColumn('students', 'city')) {
    // Does city column exist in students table?
}
```

```console
==> command
php artisan make:migration add_percentage_column_to_students_table --table=students  
php artisan make:migration modifications_to_students_table --table=students
php artisan make:migration modify_email_column --table=students
php artisan make:migration modify_tables

==> 2023_07_02_121721_add_percentage_column_to_students_table.php
public function up(): void
{
    Schema::table('students', function (Blueprint $table) {
        $table->float('percentage', 3, 2)->after('student_name');    
    });
}

==> 2023_07_02_155044_modifications_to_students_table.php
==> Note: To use renameColumn - install doctrine/dbal [composer require doctrine/dbal]
public function up(): void
{
    Schema::table('students', function (Blueprint $table) {
        $table->renameColumn('student_email', 'email');
        $table->renameColumn('student_name', 'name');
        $table->integer("percentage")->unsigned()->default(100)->comment('For Percentage')->change();
        $table->date("dob")->default(date('Y-m-d'))->comment('For DOB')->after('id');
        $table->dropColumn('city');
    });
}

==> 2023_07_02_161207_modify_email_column.php
public function up(): void
{
    Schema::table('students', function (Blueprint $table) {
        $table->string("email", 200)->default("test@example.com")->change();
    });
}

==> 2023_07_02_172149_modify_tables.php
public function up(): void
{
    Schema::dropIfExists("users");
    Schema::rename("students", "employees");
}

==> command
php artisan migrate
```

# Constraints with Migration

- MySQL Constraints
    - NOT NULL          :   $table->string('name', 100)->nullable();
    - UNIQUE            :   $table->string('email', 100)->unique();  / $table->unique('email');
    - DEFAULT           :   $table->date('dob')->default(date('Y-m-d'));
    - PRIMARY KEY       :   $table->primary('id');
    - FOREIGN KEY       :   $table->foreign('user_id')->references('id')->on('users');
    - CHECK             :   DB::statement('ALTER TABLE users ADD CONSTRAINT age CHECK(age > 18)');
- Laravel Modifiers
    - Refer Laravel Images Folder

# Constraints : Primary and Foreign Key

- Foreign Key with Cascade and Restrict
    - cascadeOnUpdate();
    - restrictOnUpdate();
    - cascadeOnDelete();
    - restrictOnDelete();
    - nullOnDelete();
- 3 Ways to make Foreign Key
```console
==> 1st Way
$table->unsignedBigInteger("student_city");
$table->foreign("student_city")->references("city_id")->on("cities");

==> 2nd Way
$table->foreignId('stu_id')->constrained('students');

==> 3rd Way
$table->unsignedBigInteger("student_id");
$table->foreignId('stu_id')->constrained();
```       
- Drop Key Constraints
```console
$table->dropPrimary('users_id_primary');
$table->dropUnique('users_email_unique');
$table->dropForeign('posts_user_id_foreign');
$table->dropForeign(['user_id']);
```

```console
==> commands
php artisan make:migration create_students_table 
php artisan make:migration create_cities_table 

==> 2023_07_02_174658_create_cities_table.php
public function up(): void
{
    Schema::create('cities', function (Blueprint $table) {
        $table->unsignedBigInteger("city_id")->autoIncrement();
        $table->string("city_name");
    });
}

==> 2023_07_02_174658_create_students_table.php
public function up(): void
{
    Schema::create('students', function (Blueprint $table) {
        $table->id("student_id");
        $table->string("student_name", 100);
        $table->unsignedBigInteger("student_city")->nullable();
        $table->foreign("student_city")->references("city_id")->on("cities")->constrained()->onUpdate("cascade")->onDelete("set null");
    });
}

==> commands
php artisan migrate
```

# Seeders

- Remember
    - While creating database - go plural
    - While creating model and seeder - go singular
- Steps to work in Model
    - Create Database
    - Create Database Migration (Create Tables in Database)
    - Seeding (Insert Initial Data in the Tables)
        - Seeder (Real Data)
        - Factory (Fake Data)
    - Create Model
- Steps to work in Seeder
    - php artisan make:modle student
    - php artisan make:seeder StudentSeeder
    - Write your code in StudentSeeder File
    - Update - Seeders/DatabaseSeeder.php file
    - php artisan db:seed

```console
run: php artisan make:model employee
run: php artisan make:seeder EmployeeSeeder

==> EmployeeSeeder.php File
<?php
namespace Database\Seeders;
use Illuminate\Database\Console\Seeds\WithoutModelEvents;
use Illuminate\Database\Seeder;
use App\Models\employee;   (added)

class EmployeeSeeder extends Seeder
{
    public function run(): void
    {
        // Added Below Code
        employee::create([
            "emp_name" => "Manish",
            "emp_email" => "sajan@gmail.com",
            "emp_city" => "Bhopal"
        ]);
    }
}

==> DatabaseSeeder.php File
<?php
namespace Database\Seeders;

// use Illuminate\Database\Console\Seeds\WithoutModelEvents;
use Illuminate\Database\Seeder;

class DatabaseSeeder extends Seeder
{
    public function run(): void
    {
        // Added Below Code
        $this->call([
            EmployeeSeeder::class
        ]);
    }
}

run: php artisan db:seed     (or)
run: php artisan db:seed --class=UserSeeder    (To run a specific seeder class file)
run: php artisan db:seed --class=UserSeeder --force    (forefully on production server)

==> Seed multiple data rows
==> EmployeeSeeder.php File
<?php
namespace Database\Seeders;
use Illuminate\Database\Console\Seeds\WithoutModelEvents;
use Illuminate\Database\Seeder;
use App\Models\employee;   (added)

class EmployeeSeeder extends Seeder
{
    public function run(): void
    {
        // Added Below Code
        $employees = collect(
            [
                [
                    "emp_name" => "Sanjay",
                    "emp_email" => "sanjay@gmail.com",
                    "emp_city" => "Jabalpur"
                ],
                [
                    "emp_name" => "Manish",
                    "emp_email" => "manish@gmail.com",
                    "emp_city" => "Indore"
                ],
                [
                    "emp_name" => "Simran",
                    "emp_email" => "simran@gmail.com",
                    "emp_city" => "Bhopal"
                ],
                [
                    "emp_name" => "Geet",
                    "emp_email" => "geet@gmail.com",
                    "emp_city" => "Sehore"
                ]
            ]
        );

        $employees->each(function ($employee) {
            employee::insert($employee);
        });
    }
}

run: php artisan migrate:fresh --seed

==> employees.json file   [database/json/employees.json]
[
    {
        "emp_name": "ABCD",
        "emp_email": "abcd@gmail.com",
        "emp_city": "ABCD"
    },
    {
        "emp_name": "EFGH",
        "emp_email": "efgh@gmail.com",
        "emp_city": "EFGH"
    },
    {
        "emp_name": "IJKL",
        "emp_email": "ijkl@gmail.com",
        "emp_city": "IJKL"
    },
    {
        "emp_name": "MNOP",
        "emp_email": "mnop@gmail.com",
        "emp_city": "MNOP"
    }
]

==> EmployeeSeeder.php File
<?php
namespace Database\Seeders;
use Illuminate\Database\Console\Seeds\WithoutModelEvents;
use Illuminate\Database\Seeder;
use App\Models\employee;   (added)
use Illuminate\Support\Facades\File;   (added)

class EmployeeSeeder extends Seeder
{
    public function run(): void
    {
        // Added Below Code
        $json = File::get('database/json/employees.json');
        $employees = collect(json_decode($json));

        // We have to use create method not insert method
        $employees->each(function ($employee) {
            employee::create([
                "emp_name" => $employee->emp_name,
                "emp_email" => $employee->emp_email,
                "emp_city" => $employee->emp_city,
            ]);
        });
    }
}

run: php artisan db:seed    (or)
run: php artisan db:seed --force  [on production server]  (or)
run: php artisan migrate:fresh --seed

==> EmployeeSeeder.php File
<?php
namespace Database\Seeders;
use Illuminate\Database\Console\Seeds\WithoutModelEvents;
use Illuminate\Database\Seeder;
use App\Models\employee;   (added)

class EmployeeSeeder extends Seeder
{
    public function run(): void
    {
        // Added Below Code
        for ($i = 1; $i <= 20; $i++) {
            employee::create([
                "emp_name" => fake()->name(),
                "emp_email" => fake()->unique()->email(),
                "emp_city" => fake()->city(),
            ]);
        }
    }
}

run: php artisan migrate:fresh --seed
```

# Query Builder : Read Data

- Steps to work with Database
    - Create Database
    - Create Database Migration (Create Tables in Database)
    - Seeding (Insert Initial Data in the Tables)
    - Create Model (SQL Commands)
        - Query Builder (Controllers)
        - Eloquent ORM (Models)
- Query Builder
    - Can perfrom CRUD (Create, Read, Update, Delete) Operations
    - Fast Database Coding
    - It protects your application from SQL injection attacks by using PDO parameter binding.
    - It works with all of Laravel's supported database systems, such as MySQL, PostgreSQL, SQLite, and SQL Server. 
- Steps to work in Query Builder
    - php artisan make:controller EmployeeController  
    - In controller file use DB Facade and write Query Builder Code in a function
    - Create the route for the Controller's Function    
- Read Data with Query Builder
    - Refer Laravel Images Folder

```console
$employee = DB::table("employees")->find(5);
return $employee;

$employee = DB::table("employees")->where('id', $id)->get();
return $employee;

$employee = DB::table("employees")
    ->select('name', 'age', 'city as emp_city')
    ->where('age', "=", 24)
    ->get();
return $employee;

$employee = DB::table("employees")
    ->select('city')
    ->distinct()
    ->get();
return $employee;

$employee = DB::table("employees")
    ->pluck('name', 'city');
return $employee;

$employee = DB::table("employees")
    ->select('*')
    ->where('age', '<>', '23')
    ->where('name', 'like', 'k%')
    ->get();
return $employee;

$employee = DB::table("employees")
    ->select('*')
    ->where([
        ['age', '>', '23'],
        ['name', 'like', 's%']
    ])
    ->get();
return $employee;

$employee = DB::table("employees")
    ->select('*')
    ->where('age', '>', '34')
    ->orWhere('name', 'like', 'k%')
    ->get();
return $employee;

$employee = DB::table("employees")
    ->select('*')
    ->whereBetween('id', [3, 6])
    ->get();
return $employee;

$employee = DB::table("employees")
    ->select('*')
    ->orWhereBetween('id', [3, 6])
    ->get();
return $employee;

$employee = DB::table("employees")
    ->select('*')
    ->whereNotBetween('age', [18, 32])
    ->get();
return $employee;

$employee = DB::table("employees")
    ->select('*')
    ->orWhereNotBetween('age', [18, 32])
    ->get();
return $employee;

$employee = DB::table("employees")
    ->select('*')
    ->whereIn('id', [1, 5, 7])
    ->get();
return $employee;

$employee = DB::table("employees")
    ->select('*')
    ->whereIn('city', ['Bhopal', 'Mumbai'])
    ->get();
return $employee;

$employee = DB::table("employees")
    ->select('*')
    ->whereNotIn('id', [1, 5, 7])
    ->get();
return $employee;

$employee = DB::table("employees")
    ->select('*')
    ->orWhereIn('id', [1, 5, 7])
    ->get();
return $employee;

$employee = DB::table("employees")
    ->select('*')
    ->orWhereNotIn('id', [1, 5, 7])
    ->get();
return $employee;

$employee = DB::table("employees")
    ->select('*')
    ->whereNull('city')
    ->get();
return $employee;

$employee = DB::table("employees")
    ->select('*')
    ->whereNotNull('city')
    ->get();
return $employee;

$employee = DB::table("employees")
    ->select('*')
    ->whereDate('created_at', "2023-07-04")
    ->get();
return $employee;

$employee = DB::table("employees")
    ->select('*')
    ->whereDate("created_at", "=", "2023-07-01")
    ->get();
return $employee;

$employee = DB::table("employees")
    ->select('*')
    ->whereMonth("created_at", "=", "6")
    ->get();
return $employee;

$employee = DB::table("employees")
    ->select('*')
    ->whereDay("created_at", "=", "1")
    ->get();
return $employee;

$employee = DB::table("employees")
    ->select('*')
    ->whereYear("created_at", "=", "2022")
    ->get();
return $employee;

$employee = DB::table("employees")
    ->select('*')
    ->whereTime("created_at", ">=", "17:39")
    ->get();
return $employee;   

if (DB::table("employees")->where('id', 10)->exists()) {
    return true;
} else {
    return false;
}

if (DB::table("employees")->where('id', 15)->doesntExist()) {
    return "Doesn't Exist";
} else {
    return "Does Exist";
}

$employee = DB::table("employees")
    ->select('*')
    ->orderBy("name", "desc")
    ->get();
return $employee;

$employee = DB::table("employees")
    ->select('*')
    ->orderByRaw("age asc, name desc")
    ->get();
return $employee;

$employee = DB::table("employees")
    ->select('*')
    ->orderBy("age", "asc")
    ->orderBy("name", "desc")
    ->get();
return $employee;

$employee = DB::table("employees")
    ->first();
return $employee;

$employee = DB::table("employees")
    ->latest()
    ->first();
return $employee;

$employee = DB::table("employees")
    ->oldest()
    ->first();
return $employee;

$employee = DB::table("employees")
    ->inRandomOrder()
    ->first();
return $employee;

$employee = DB::table("employees")
    ->limit(3)
    ->get();
return $employee;

$employee = DB::table("employees")
    ->limit(3)
    ->offset(3)
    ->get();
return $employee;

$employee = DB::table("employees")
    ->take(3)
    ->skip(3)
    ->get();
return $employee;

$employee = DB::table("employees")
    ->count();
return $employee;

$employee = DB::table("employees")
    ->max('age');
return $employee;

$employee = DB::table("employees")
    ->min('age');
return $employee;

$employee = DB::table("employees")
    ->avg('age');
return $employee;

$employee = DB::table("employees")
    ->sum('age');
return $employee;
```   

# Query Builder : Determine If Records Exist?

```console
if (DB::table("employees")->where('id', 10)->exists()) {
    return true;
} else {
    return false;
}

if (DB::table("employees")->where('id', 15)->doesntExist()) {
    return "Doesn't Exist";
} else {
    return "Does Exist";
}
```

# Factory

- Factory generates Fake Data
- Can generate Relationship Data
- Refer: https://fakerphp.github.io/
- Factory Related Commands
    - php artisan make:factory UserFactory
    - php artisan make:factory UserFactory --model=student
    - php artisan make:model student -f
    - php artisan db:seed
    - php artisan db:seed --class=UserSeeder
    - php artisan migrate:fresh --seed
- Steps to work in Factory
```console
php artisan make:migration create_students_table

=> students migration file
public function up(): void
{
    Schema::create('students', function (Blueprint $table) {
        $table->id();
        $table->string("name", 30);
        $table->integer("age");
        $table->string("email", 40)->nullable()->unique();
        $table->string("address");
        $table->string("city");
        $table->string("phone");
        $table->string("password");            
        $table->timestamps();
    });
}

php artisan migrate

php artisan make:factory StudentFactory

=> student factory file
public function definition(): array
{
    return [
        "name" => fake()->name(),
        "age" => fake()->numberBetween(15, 25),
        "email" => fake()->email(),
        "address" => fake()->address(),
        "city" => fake()->city(),
        "phone" => fake()->phoneNumber(),
        "address" => fake()->address(),
        "password" => fake()->password()
    ];
}

php artisan make:model student

=> DatabaseSeeder File
use App\Models\student;   (added)
use App\Models\user;   (added)
public function run(): void
{
    student::factory()->count(10)->create();
    user::factory(5)->create();
}

php artisan db:seed
php artisan migrate:fresh --seed

We can also keep factory code (student::factory()->count(10)->create()) in the StudentSeeder file not directly in DatabaseSeeder file. Then, we can use call method in DatabaseSeeder file where we have to give the name of StudentSeeder. (Same is the case with Seeders)
```

# Query Builder : Create, Update, and Delete

- Insert
    - insert method with single and multiple array records
    - turn off timestamps
    - upsert method ([...], ['email', 'name'], ['city'])    
        - it updates the record columns' values if email is found duplicate or insert the new one
        - first array contains the record to be added
        - second array contains names of columns that are unique
        - third array contains names of columns whose values to be updated
    - insertOrIgnore (in case if email gets duplicated - runs else condition)
    - if(....) => true/false condition
    - insertGetId (returns the id of the inserted record)
- Update
    - update method with where condition
    - update method with where condition with if/else condition
    - You all where types like whereNull, whereBetween etc. Can give multiple where conditions
    - updateOrInsert Method ([], [])
        - first array takes column values which needs to be checked - are they in the table or not?
        - if not found a new record gets inserted and if found the second array columns' values gets updated
    - increment method with where condition ('age', 5)  - increments age column value by 5 - default is 1
    - decrement method with where condition ('age', 5)  - decrements age column value by 5 - default is 1
    - increment and decrement method also takes third parameter
    - incrementEach & decrementEach method for mutliple increments/decrements operations - takes array
- Delete
    - delete method with where condition
    - pass id from the route
    - delete button, once delete get back to the prev page with redirect()->route() method
    - delete without where clause
    - truncate method - it deletes all records and reset the id to 1 

# Query Builder With Forms

