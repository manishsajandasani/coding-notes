# How to create Global Functions that can be accessed from any Controller and Blade file in Laravel?

- Create a new Helpers folder in your app directory.
- Create a php file named your_helper_function.php in that Helpers directory.
- Add your function(s) inside your_helper_function.php
```console
function your_function($parameters){
    //function logic
} 

function your_another_function($parameters){
    //function logic
} 
```
- Add this file to the Files key of your composer.json like
```console
"autoload": {
    ...
    "files": [
        "app/Helpers/your_helper_function.php"
    ]
    ...
}
```
- Finally, regenerate composer autoload files. 
- Run Command: **composer dump-autoload**  (Run this in your project directory)
- That's it! and now you can access your_function() or your_another_function() in any part of your Laravel project.

# Create a global file to have global variables and arrays

- Create a file ____.php and place it inside the config folder
```console
return [
    'website_name' => "SMH Bhopal",
    'admin_panel_name' => "Admin | SMH Bhopal",
    'favicon' => "images/logo/smh-favicon.png",
    'address' => "Hoshangabad Road, Bhopal",
    "about-sub-menu" => [
        (object)["name" => "Management", "slug" => "about.management"],
        (object)["name" => "Vision & Mission", "slug" => "about.vision-mission"],
        (object)["name" => "Why SMH?", "slug" => "about.whysmh"],
        (object)["name" => "Accreditations", "slug" => "about.accreditations"],
    ],
    "doctors" => [
        "images/fake-doctors/doctor-1.jpg",
        "images/fake-doctors/doctor-2.jpg",
        "images/fake-doctors/doctor-3.jpg",
        "images/fake-doctors/doctor-4.jpg"
    ],
]

{{ asset(Config::get('global.favicon')) }}
```

# If you can't access a Route but it exists

- php artisan route:clear
- php artisan route:cache
- php artisan route:list

# Laravel Intervention Image Package Installation

- composer require intervention/image
- config/app.php
    - add (Intervention\Image\ImageServiceProvider::class) in providers array
    - add ('Image' => Intervention\Image\Facades\Image::class) in aliases array
- Controller File
    - use Image;
    - $default_img = $request->dept_icon;
      $imageName = time() . '.' . $default_img->getClientOriginalExtension();  
      $image = Image::make($default_img->getRealPath());
      $image->save(public_path('upload/dept_icons/').$imageName);
- Make sure turn on GD Library extension in php.ini file
- Restart Xampp and Laravel Server after performing all above steps

# If you are getting the below error
# SQLSTATE[HY000] [1045] Access denied for user 'DBname'@'localhost' (using password: YES) (SQL: select * from `users` where `id` = 9 limit 1)

- There could be many reasons behind this error and one of them is that you used # symbol in the DB_PASSWORD
    - simple wrap DB_USERNAME="xyz" DB_PASSWORD="123" values with double quotes 
- You can also run the following commands:
    - php artisan route:cache
    - php artisan route:clear
    - php artisan config:clear
    - php artisan cache:clear
    - php artisan optimize
- Make sure to give unique names to routes. Don't give same routes names even if their HTTP Verbs are different like GET and POST
- Don't upload .git and node_modules folder on the server 

# To check whether view file exists or not in the blade file
```console
@if(\View::exists("front.coe.technology.$slugName-technology"))
    @include("front.coe.technology.$slugName-technology")
@endif
```