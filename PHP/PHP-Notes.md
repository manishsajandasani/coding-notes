# PHP Basics

## What is PHP?

- PHP is a widely-used open source server side scripting language.
- PHP is an acronym for "PHP: Hypertext Preprocessor".
- PHP is free to download and use.
- It is a powerful tool for making dynamic and interactive Web pages.
- PHP code is executed on the server.
- Before you learn PHP you should have a basic understanding of the following:
  - HTML
  - CSS
  - JavaScript
- PHP is an amazing and popular language!
- It is powerful enough to be at the core of the biggest blogging system on the web (WordPress)!
- It is deep enough to run large social networks!
- It is also easy enough to be a beginner's first server side language!

## What is a PHP File?

- PHP files can contain text, HTML, CSS, JavaScript, and PHP code.
- PHP code/script is executed on the server, and the plain HTML result is sent back to the browser.
- PHP files have extension of ".php".

## What Can PHP Do?

- PHP can generate dynamic page content.
- PHP can create, open, read, write, delete, and close files on the server.
- PHP can collect form data.
- PHP can send and receive cookies.
- PHP can read, add, delete, modify data in your database.
- PHP can be used to control user-access.
- PHP can encrypt data.
- With PHP you are not limited to output HTML. You can output images or PDF files.
- You can also output any text, such as XHTML and XML.

## Why PHP?

- PHP runs on various platforms (Windows, Linux, Unix, Mac OS X, etc.).
- PHP is compatible with almost all servers used today (Apache, IIS, etc.).
- PHP supports a wide range of databases.
- PHP is free. Download it from the official PHP resource: www.php.net.
- PHP is easy to learn and runs efficiently on the server side.

## Basic PHP Syntax

- A PHP script can be placed anywhere in the document.- A PHP script starts with `<?php` and ends with `?>`.

```php
<?php
// PHP code goes here
?>
```

- The default file extension for PHP files is `.php`.
- A PHP file normally contains HTML tags, and some PHP scripting code.

```php
<!DOCTYPE html>
<html>
<body>

<h1>My first PHP page</h1>

<?php
echo "Hello World!";
?>

</body>
</html>
```

## PHP Case Sensitivity

- In PHP, keywords `(e.g. if, else, while, echo, etc.)`, classes, functions, and user-defined functions are not case-sensitive.

```php
<!DOCTYPE html>
<html>
<body>

<?php
ECHO "Hello World!<br>";
echo "Hello World!<br>";
EcHo "Hello World!<br>";
?>

</body>
</html>
```

- However; all variable names are case-sensitive!
- Look at the example below: The variables `$color`, `$COLOR`, and `$coLOR` are treated as three different variables:

```php
<!DOCTYPE html>
<html>
<body>

<?php
$color = "red";
echo "My car is " . $color . "<br>";
echo "My house is " . $COLOR . "<br>";
echo "My boat is " . $coLOR . "<br>";
?>

</body>
</html>
```

## PHP Comments

- A comment in PHP code is a line that is not executed as a part of the program.
- Its only purpose is to be read by someone who is looking at the code.
- Comments can be used to:
  - Let others understand your code.
  - Remind yourself of what you did - Most programmers have experienced coming back to their own work a year or two later and having to re-figure out what they did.
  - Comments can remind you of what you were thinking when you wrote the code.
- PHP supports several ways of commenting:
  - Can give Single line comments using `//` and `#`
  - Can give Multiple lines comment using `/*  */`

```php
<!DOCTYPE html>
<html>
<body>

<?php
// This is a single-line comment

# This is also a single-line comment

/*
This is a multiple-lines comment block
that spans over multiple
lines
*/

// You can also use comments to leave out parts of a code line
$x = 5 /* + 15 */ + 5;
echo $x;
?>

</body>
</html>
```

## PHP Variables

- Think of variables as containers for storing data.
- In PHP, a variable starts with the $ sign, followed by the name of the variable:

```php
<?php
$txt = "Hello world!";
$x = 5;
$y = 10.5;
?>
```

- **Note:** When you assign a text value to a variable, put quotes around the value.
- **Note:** Unlike other programming languages, PHP has no command for declaring a variable. It is created the moment you first assign a value to it.

## Naming Convention for Variables

- A variable can have a short name (like x and y) or a more descriptive name (age, carname, total_volume).
- Rules for PHP variables:
  - A variable starts with the $ sign, followed by the name of the variable.
  - A variable name must start with a letter or the underscore character.
  - A variable name cannot start with a number.
  - A variable name can only contain alpha-numeric characters and underscores (A-z, 0-9, and \_ ).
  - Variable names are case-sensitive (`$age` and `$AGE` are two different variables).
- To output variables:
  - The PHP `echo` statement is often used to output data to the screen.

```php
<?php
$txt = "W3Schools.com";
echo "I love $txt!";
echo "I love " . $txt . "!";

$x = 5;
$y = 4;
echo $x + $y;
?>
```

## PHP is a Loosely Typed Language

- In the example above, notice that we did not have to tell PHP which data type the variable is.
- PHP automatically associates a data type to the variable, depending on its value. Since the data types are not set in a strict sense, you can do things like adding a string to an integer without causing an error.
- In PHP 7, type declarations were added. This gives an option to specify the data type expected when declaring a function, and by enabling the strict requirement, it will throw a "Fatal Error" on a type mismatch.

## PHP Variables Scope

- In PHP, variables can be declared anywhere in the script.
- The scope of a variable is the part of the script where the variable can be referenced/used.
- PHP has three different variable scopes:
  - local
  - global
  - static
- A variable declared outside a function has a GLOBAL SCOPE and can only be accessed outside a function

```php
<?php
$x = 5; // global scope

function myTest() {
  // using x inside this function will generate an error
  echo "<p>Variable x inside function is: $x</p>";
}
myTest();

echo "<p>Variable x outside function is: $x</p>";
?>
```

- A variable declared within a function has a LOCAL SCOPE and can only be accessed within that function:

```php
<?php
function myTest() {
  $x = 5; // local scope
  echo "<p>Variable x inside function is: $x</p>";
}
myTest();

// using x outside the function will generate an error
echo "<p>Variable x outside function is: $x</p>";
?>
```

- You can have local variables with the same name in different functions, because local variables are only recognized by the function in which they are declared.
- The global keyword is used to access a global variable from within a function.
- To do this, use the global keyword before the variables (inside the function):

```php
<?php
$x = 5;
$y = 10;

function myTest() {
  global $x, $y;
  $y = $x + $y;
}

myTest();
echo $y; // outputs 15
?>
```

- PHP also stores all global variables in an array called `$GLOBALS[index]`. The index holds the name of the variable. This array is also accessible from within functions and can be used to update global variables directly.

```php
<?php
$x = 5;
$y = 10;

function myTest() {
  $GLOBALS['y'] = $GLOBALS['x'] + $GLOBALS['y'];
}

myTest();
echo $y; // outputs 15
?>
```

## PHP The static Keyword

- Normally, when a function is completed/executed, all of its variables are deleted. However, sometimes we want a local variable NOT to be deleted. We need it for a further job.
- To do this, use the static keyword when you first declare the variable:

```php
<?php
function myTest() {
  static $x = 0;
  echo $x;
  $x++;
}

myTest();
myTest();
myTest();
?>
```

- Then, each time the function is called, that variable will still have the information it contained from the last time the function was called.
- Note: The variable is still local to the function.

## PHP `echo` and `print` Statements

- With PHP, there are two basic ways to get output: `echo` and `print`.
- `echo` and `print` are more or less the same. They are both used to output data to the screen.
- Differences:
  - `echo` has no return value while `print` has a return value of 1 so it can be used in expressions.
  - `echo` can take multiple parameters (although such usage is rare) while `print` can take one argument.
  - `echo` is marginally faster than `print`.
- The `echo` statement can be used with or without parentheses: `echo` or `echo()`.
- The `print` statement can be used with or without parentheses: `print` or `print()`.
- **Notice** that the text can contain HTML markup.

```php
<?php
echo "<h2>PHP is Fun!</h2>";
echo "Hello world!<br>";
echo "I'm about to learn PHP!<br>";
echo "This ", "string ", "was ", "made ", "with multiple parameters.";

$txt1 = "Learn PHP";
$txt2 = "W3Schools.com";
$x = 5;
$y = 4;
echo "<h2>" . $txt1 . "</h2>";
echo "Study PHP at " . $txt2 . "<br>";
echo $x + $y;

print "<h2>PHP is Fun!</h2>";
print "Hello world!<br>";
print "I'm about to learn PHP!";

$txt1 = "Learn PHP";
$txt2 = "W3Schools.com";
$x = 5;
$y = 4;
print "<h2>" . $txt1 . "</h2>";
print "Study PHP at " . $txt2 . "<br>";
print $x + $y;
?>
```

## PHP var_dump function

- The var_dump() function dumps information about one or more variables.
- The information holds type and value of the variable(s).

```php
<?php
$a = 32;
echo var_dump($a) . "<br>";

$b = "Hello world!";
echo var_dump($b) . "<br>";

$c = 32.5;
echo var_dump($c) . "<br>";

$d = array("red", "green", "blue");
echo var_dump($d) . "<br>";

$e = array(32, "Hello world!", 32.5, array("red", "green", "blue"));
echo var_dump($e) . "<br>";

// Dump two variables
echo var_dump($a, $b) . "<br>";
?>
```

## PHP Data Types

- Variables can store data of different types, and different data types can do different things.
- PHP supports the following data types:
  - String
  - Integer
  - Float (floating point numbers - also called double)
  - Boolean
  - Array
  - Object
  - NULL
  - Resource
- **PHP String**
  - A string is a sequence of characters, like "Hello world!".
  - A string can be any text inside quotes.
  - You can use single or double quotes.

```php
<?php
$x = "Hello world!";
$y = 'Hello world!';

echo $x;
echo "<br>";
echo $y;
?>
```

- **PHP Integer**
  - An integer data type is a non-decimal number between -2,147,483,648 and 2,147,483,647.
  - Rules for integers:
    - An integer must have at least one digit.
    - An integer must not have a decimal point.
    - An integer can be either positive or negative.
    - Integers can be specified in: decimal (base 10), hexadecimal (base 16), octal (base 8), or binary (base 2) notation.
  - In the following example `$x` is an integer. The PHP `var_dump()` function returns the data type and value:

```php
<?php
$x = 5985;
var_dump($x);
?>
```

- **PHP Float**

  - A float (floating point number) is a number with a decimal point or a number in exponential form.
  - In the following example `$x` is a float. The PHP `var_dump()` function returns the data type and value:

```php
<?php
$x = 10.365;
var_dump($x);
?>
```

- **PHP Boolean**

  - A Boolean represents two possible states: TRUE or FALSE.
  - Booleans are often used in conditional testing.

```php
<?php
$x = true;
$y = false;
?>
```

- **PHP Array**

  - An array stores multiple values in one single variable.
  - In the following example `$cars` is an array. The PHP `var_dump()` function returns the data type and value:

```php
<?php
$cars = array("Volvo","BMW","Toyota");
var_dump($cars);
?>
```

- **PHP Object**

  - Classes and objects are the two main aspects of object-oriented programming.
  - A class is a template for objects, and an object is an instance of a class.
  - When the individual objects are created, they inherit all the properties and behaviors from the class, but each object will have different values for the properties.
  - Let's assume we have a class named `Car`. A Car can have properties like model, color, etc. We can define variables like `$model`, `$color`, and so on, to hold the values of these properties.
  - When the individual objects `(Volvo, BMW, Toyota, etc.)` are created, they inherit all the properties and behaviors from the class, but each object will have different values for the properties.
  - If you create a `__construct()` function, PHP will automatically call this function when you create an object from a class.

```php
<?php
$cars_object = (object)["Volvo","BMW","Toyota"];
print_r($cars_object);

// Object Oriented Way
class Car {
  public $color;
  public $model;
  public function __construct($color, $model) {
    $this->color = $color;
    $this->model = $model;
  }
  public function message() {
    return "My car is a " . $this->color . " " . $this->model . "!";
  }
}

$myCar = new Car("black", "Volvo");
echo $myCar->message();
echo "<br>";
$myCar = new Car("red", "Toyota");
echo $myCar->message();
?>
```

- **PHP NULL Value**

  - Null is a special data type which can have only one value: NULL.
  - A variable of data type NULL is a variable that has no value assigned to it.
  - **Tip:** If a variable is created without a value, it is automatically assigned a value of NULL.
  - Variables can also be emptied by setting the value to NULL:

```php
<?php
$x = "Hello world!";
$x = null;
var_dump($x);
?>
```

- **PHP Resource**

  - The special resource type is not an actual data type. It is the storing of a reference to functions and resources external to PHP.
  - A common example of using the resource data type is a database call.

## PHP Constants

- Constants are like variables except that once they are defined they cannot be changed or undefined.
- A constant is an identifier (name) for a simple value. The value cannot be changed during the script.
- A valid constant name starts with a letter or underscore (no $ sign before the constant name).
- Note: Unlike variables, constants are automatically global across the entire script.
- To create a constant, use the `define()` function.
- **Syntax:** `define(name, value)`
- **Parameters:**
  - **name:** Specifies the name of the constant
  - **value:** Specifies the value of the constant

```php
<?php
define("GREETING", "Welcome to W3Schools.com!");
echo GREETING;
?>
```

- In PHP7, you can create an Array constant using the define() function.

```php
<?php
define("cars", [
  "Alfa Romeo",
  "BMW",
  "Toyota"
]);
echo cars[0];
?>

<?php
define("GREETING", "Welcome to W3Schools.com!");

function myTest() {
  echo GREETING;
}

myTest();
?>
```

## PHP Operators

- Operators are used to perform operations on variables and values.
- PHP divides the operators in the following groups:
  - Arithmetic operators
  - Assignment operators
  - Comparison operators
  - Increment/Decrement operators
  - Logical operators
  - String operators
  - Array operators
  - Conditional assignment operators
- **PHP Arithmetic Operators**
  - The PHP arithmetic operators are used with numeric values to perform common arithmetical operations, such as addition, subtraction, multiplication etc.
    - Addition => `$x + $y`
    - Subtraction => `$x - $y`
    - Multiplication => `$x * $y`
    - Division => `$x / $y`
    - Modulus => `$x % $y`
    - Exponentiation => `$x ** $y`
- **PHP Assignment Operators**
  - The PHP assignment operators are used with numeric values to write a value to a variable.
  - The basic assignment operator in PHP is `=`. It means that the left operand gets set to the value of the assignment expression on the right.
    - Simple Assignment => `$x = $y` => `$x = $y`
    - Addition with Assignment => `$x += $y` => `$x = $x + $y`
    - Subtraction with Assignment => `$x -= $y` => `$x = $x - $y`
    - Multiplication with Assignment => `$x *= $y` => `$x = $x * $y`
    - Division with Assignment => `$x /= $y` => `$x = $x / $y`
    - Modulus with Assignment => `$x %= $y` => `$x = $x % $y`
    - Exponentiation with Assignment => `$x **= $y` => `$x = $x ** $y`
- **PHP Comparison Operators**
  - The PHP comparison operators are used to compare two values (number or string).
    - Equal => `$x == $y` => Returns true if `$x` is equal to `$y`
    - Identical => `$x === $y` => Returns true if `$x` is equal to `$y`, and they are of the same type
    - Not Equal => `$x != $y` => Returns true if `$x` is not equal to `$y`
    - Not Equal => `$x <> $y` => Returns true if `$x` is not equal to `$y`
    - Not Identical => `$x !== $y` => Returns true if `$x` is not equal to `$y`, or they are not of the same type
    - Greater Than => `$x > $y` => Returns true if `$x` is greater than `$y`
    - Less Than => `$x < $y` => Returns true if `$x` is less than `$y`
    - Greater Than or Equal To => `$x >= $y` => Returns true if `$x` is greater than or equal to `$y`
    - Less Than or Equal To => `$x <= $y` => Returns true if `$x` is less than or equal to `$y`
    - Spaceship => `$x <=> $y` => Returns an integer less than, equal to, or greater than zero, depending on if `$x` is less than, equal to, or greater than `$y`. Introduced in PHP 7.
- **PHP Increment / Decrement Operators**
  - The PHP increment operators are used to increment a variable's value.
  - The PHP decrement operators are used to decrement a variable's value.
    - Pre-increment => `++$x` => Increments `$x` by one, then returns `$x`
    - Post-increment => `$x++` => Returns `$x`, then increments `$x` by one
    - Pre-decrement => `--$x` => Decrements `$x` by one, then returns `$x`
    - Post-decrement => `$x--` => Returns `$x`, then decrements `$x` by one
- **PHP Logical Operators**
  - The PHP logical operators are used to combine conditional statements.
    - and => `$x and $y` => True if both `$x` and `$y` are true
    - or => `$x or $y` => True if either `$x` or `$y` is true
    - xor => `$x xor $y` => True if either `$x` or `$y` is true, but not both
    - && => `$x && $y` => True if both `$x` and `$y` are true
    - || => `$x || $y` => True if either `$x` or `$y` is true
    - ! => `!$x` => True if `$x` is not true
- **PHP String Operators**
  - PHP has two operators that are specially designed for strings.
    - Concatenation => `.` => `$txt1 . $txt2` => Concatenation of `$txt1` and `$txt2`
    - Concatenation Assignment => `.=` => `$txt1 .= $txt2` => Appends `$txt2` to `$txt1`
- **PHP Array Operators**
  - The PHP array operators are used to compare arrays.
    - Union => `$x + $y` => Union of `$x` and `$y`
    - Equality => `$x == $y` => Returns true if `$x` and `$y` have the same key/value pairs
    - Identity => `$x === $y` => Returns true if `$x` and `$y` have the same key/value pairs in the same order and of the same types
    - Inequality => `$x != $y` => Returns true if `$x` is not equal to `$y`
    - Inequality => `$x <> $y` => Returns true if `$x` is not equal to `$y`
    - Non-Identity => `$x !== $y` => Returns true if `$x` is not identical to `$y`
- **PHP Conditional Assignment Operators**
  - The PHP conditional assignment operators are used to set a value depending on conditions.
    - Ternary => `?:` => `$x = expr1 ? expr2 : expr3`
      - Returns the value of `$x`. The value of `$x` is expr2 if expr1 = TRUE. The value of `$x` is expr3 if expr1 = FALSE
    - Null Coalescing => `??` => `$x = expr1 ?? expr2`
      - Returns the value of `$x`. The value of `$x` is expr1 if expr1 exists, and is not NULL. If expr1 does not exist, or is NULL, the value of `$x` is expr2. Introduced in PHP 7

## Difference between undefined, null, and not-defined

- **null** means an empty value or a blank value. It is the intentional absence of the value.
- **undefined** indicates that a variable has been declared but not given a value.
- **not defined** indicates that a variable does not exist.

## PHP If...Else...Elseif

- Conditional statements are used to perform different actions based on different conditions.
- Very often when you write code, you want to perform different actions for different conditions.
- You can use conditional statements in your code to do this.
- In PHP we have the following conditional statements:
  - `if` statement - executes some code if one condition is true
  - `if...else` statement - executes some code if a condition is true and another code if that condition is false
  - `if...elseif...else` statement - executes different codes for more than two conditions
  - `switch` statement - selects one of many blocks of code to be executed
    - This is how it works: First we have a single expression `n` (most often a variable), that is evaluated once. The value of the expression is then compared with the values for each case in the structure. If there is a match, the block of code associated with that case is executed. Use `break` to prevent the code from running into the next case automatically. The `default` statement is used if no match is found.

```php
<?php
$t = date("H");

if ($t < "20") {
  echo "Have a good day!";
}
?>


<?php
$t = date("H");

if ($t < "20") {
  echo "Have a good day!";
} else {
  echo "Have a good night!";
}
?>


<?php
$t = date("H");

if ($t < "10") {
  echo "Have a good morning!";
} elseif ($t < "20") {
  echo "Have a good day!";
} else {
  echo "Have a good night!";
}
?>


<?php
$favcolor = "red";

switch ($favcolor) {
  case "red":
    echo "Your favorite color is red!";
    break;
  case "blue":
    echo "Your favorite color is blue!";
    break;
  case "green":
    echo "Your favorite color is green!";
    break;
  default:
    echo "Your favorite color is neither red, blue, nor green!";
}
?>
```

## PHP Loops

- Often when you write code, you want the same block of code to run over and over again a certain number of times.
- So, instead of adding several almost equal code-lines in a script, we can use loops.
- Loops are used to execute the same block of code again and again, as long as a certain condition is true.
- In PHP, we have the following loop types:
  - `while` - loops through a block of code as long as the specified condition is true
  - `do...while` - loops through a block of code once, and then repeats the loop as long as the specified condition is true
  - `for` - loops through a block of code a specified number of times
  - `foreach` - loops through a block of code for each element in an array
- `break` is used to "jump out" of a switch statement.
- The `break` statement can also be used to jump out of a loop.
- The `continue` statement breaks one iteration (in the loop), if a specified condition occurs, and continues with the next iteration in the loop.

```php
<?php
$x = 1;

while($x <= 5) {
  echo "The number is: $x <br>";
  $x++;
}
?>


<?php
$x = 0;

while($x <= 100) {
  echo "The number is: $x <br>";
  $x+=10;
}
?>


<?php
$x = 1;

do {
  echo "The number is: $x <br>";
  $x++;
} while ($x <= 5);
?>


<?php
for ($x = 0; $x <= 10; $x++) {
  echo "The number is: $x <br>";
}
?>


<?php
for ($x = 0; $x <= 100; $x+=10) {
  echo "The number is: $x <br>";
}
?>


<?php
$colors = array("red", "green", "blue", "yellow");

foreach ($colors as $value) {
  echo "$value <br>";
}
?>


<?php
$age = array("Peter"=>"35", "Ben"=>"37", "Joe"=>"43");

foreach($age as $x => $val) {
  echo "$x = $val<br>";
}
?>


<?php
for ($x = 0; $x < 10; $x++) {
  if ($x == 4) {
    break;
  }
  echo "The number is: $x <br>";
}
?>


<?php
$x = 0;

while($x < 10) {
  if ($x == 4) {
    break;
  }
  echo "The number is: $x <br>";
  $x++;
}
?>


<?php
$x = 0;

while($x < 10) {
  if ($x == 4) {
    $x++;
    continue;
  }
  echo "The number is: $x <br>";
  $x++;
}
?>
```

## PHP Arrays

- An array stores multiple values in one single variable.
- An array is a special variable, which can hold more than one value at a time.
- If you have a list of items (a list of car names, for example), storing the cars in single variables could look like this:

```php
$cars1 = "Volvo";
$cars2 = "BMW";
$cars3 = "Toyota";
```

- However, what if you want to loop through the cars and find a specific one? And what if you had not 3 cars, but 300?
- The solution is to create an array!
- An array can hold many values under a single name, and you can access the values by referring to an index number.
- In PHP, the array() function is used to create an array.
- In PHP, there are three types of arrays:
  - `Indexed arrays` - Arrays with a numeric index
  - `Associative arrays` - Arrays with named keys
  - `Multidimensional arrays` - Arrays containing one or more arrays
- The `count()` function is used to return the length (the number of elements) of an array.

```php
<?php
$cars = array("Volvo", "BMW", "Toyota");
echo count($cars);
?>
```

- https://www.w3schools.com/php/php_ref_array.asp
- There are two ways to create indexed arrays.
- The index can be assigned automatically and manually (index always starts at 0).

```php
$cars = array("Volvo", "BMW", "Toyota");

$cars[0] = "Volvo";
$cars[1] = "BMW";
$cars[2] = "Toyota";

<?php
$cars = array("Volvo", "BMW", "Toyota");
echo "I like " . $cars[0] . ", " . $cars[1] . " and " . $cars[2] . ".";
?>

<?php
$cars = array("Volvo", "BMW", "Toyota");
$arrlength = count($cars);

for($x = 0; $x < $arrlength; $x++) {
  echo $cars[$x];
  echo "<br>";
}
?>
```

- Associative arrays are arrays that use named keys that you assign to them.
- There are two ways to create an associative array:

```php
$age = array("Peter"=>"35", "Ben"=>"37", "Joe"=>"43");

$age['Peter'] = "35";
$age['Ben'] = "37";
$age['Joe'] = "43";

<?php
$age = array("Peter"=>"35", "Ben"=>"37", "Joe"=>"43");
echo "Peter is " . $age['Peter'] . " years old.";
?>

<?php
$age = array("Peter"=>"35", "Ben"=>"37", "Joe"=>"43");

foreach($age as $x => $x_value) {
  echo "Key=" . $x . ", Value=" . $x_value;
  echo "<br>";
}
?>
```

- A multidimensional array is an array containing one or more arrays.
- PHP supports multidimensional arrays that are two, three, four, five, or more levels deep.
- However, arrays more than three levels deep are hard to manage for most people.
- The dimension of an array indicates the number of indices you need to select an element.
  - For a two-dimensional array you need two indices to select an element.
  - For a three-dimensional array you need three indices to select an element.

```php
$cars = array (
  array("Volvo",22,18),
  array("BMW",15,13),
  array("Saab",5,2),
  array("Land Rover",17,15)
);

<?php
echo $cars[0][0].": In stock: ".$cars[0][1].", sold: ".$cars[0][2].".<br>";
echo $cars[1][0].": In stock: ".$cars[1][1].", sold: ".$cars[1][2].".<br>";
echo $cars[2][0].": In stock: ".$cars[2][1].", sold: ".$cars[2][2].".<br>";
echo $cars[3][0].": In stock: ".$cars[3][1].", sold: ".$cars[3][2].".<br>";
?>

<?php
for ($row = 0; $row < 4; $row++) {
  echo "<p><b>Row number $row</b></p>";
  echo "<ul>";
  for ($col = 0; $col < 3; $col++) {
    echo "<li>".$cars[$row][$col]."</li>";
  }
  echo "</ul>";
}
?>
```

- The elements in an array can be sorted in alphabetical or numerical order, descending or ascending.
- PHP Array Sort Functions:
  - `sort()` - sort arrays in ascending order
  - `rsort()` - sort arrays in descending order
  - `asort()` - sort associative arrays in ascending order, according to the value
  - `ksort()` - sort associative arrays in ascending order, according to the key
  - `arsort()` - sort associative arrays in descending order, according to the value
  - `krsort()` - sort associative arrays in descending order, according to the key

```php
<?php
$cars = array("Volvo", "BMW", "Toyota");
sort($cars);
?>

<?php
$numbers = array(4, 6, 2, 22, 11);
sort($numbers);
?>

<?php
$cars = array("Volvo", "BMW", "Toyota");
rsort($cars);
?>

<?php
$numbers = array(4, 6, 2, 22, 11);
rsort($numbers);
?>

<?php
$age = array("Peter"=>"35", "Ben"=>"37", "Joe"=>"43");
asort($age);
?>

<?php
$age = array("Peter"=>"35", "Ben"=>"37", "Joe"=>"43");
ksort($age);
?>

<?php
$age = array("Peter"=>"35", "Ben"=>"37", "Joe"=>"43");
arsort($age);
?>

<?php
$age = array("Peter"=>"35", "Ben"=>"37", "Joe"=>"43");
krsort($age);
?>
```

## PHP Functions

- **Complete PHP Functions Reference**
  - https://www.w3schools.com/php/php_ref_overview.asp
- PHP has over 1000 built-in functions that can be called directly, from within a script, to perform a specific task.
- Besides the built-in PHP functions, it is possible to create your own functions.
  - A function is a block of statements that can be used repeatedly in a program.
  - A function will not execute automatically when a page loads.
  - A function will be executed by a call to the function.
- A user-defined function declaration starts with the word function.
- A function name must start with a letter or an underscore. Function names are NOT case-sensitive.
- Give the function a name that reflects what the function does!

```php
<?php
function writeMsg() {
  echo "Hello world!";
}

writeMsg(); // call the function
?>
```
- **PHP Function Arguments**
  - Information can be passed to functions through arguments. An argument is just like a variable.
  - Arguments are specified after the function name, inside the parentheses. 
  - You can add as many arguments as you want, just separate them with a comma.

```php
<?php
function familyName($fname) {
  echo "Hello $fname.<br>";
}

familyName("Jani");
familyName("Hege");
familyName("Stale");
familyName("Kai Jim");
familyName("Borge");


function familyName($fname, $year) {
  echo "$fname Refsnes. Born in $year <br>";
}

familyName("Hege", "1975");
familyName("Stale", "1978");
familyName("Kai Jim", "1983");
?>
```

- As we know that PHP is a Loosely Typed Language and in the above example, we did not have to tell PHP which data type the arguments are.
- PHP automatically associates a data type to the variable, depending on its value. 
- Since the data types are not set in a strict sense, you can do things like adding a string to an integer without causing an error.  
- In PHP 7, type declarations were added. 
- This gives us an option to specify the expected data type when declaring a function, and by adding the strict declaration, it will throw a "Fatal Error" if the data type mismatches.
- To specify strict we need to set `declare(strict_types=1);`. 
- This must be on the very first line of the PHP file.
- The `strict` declaration forces things to be used in the intended way.

```php
<?php 
declare(strict_types=1); // strict requirement

function addNumbers(int $a, int $b) {
  return $a + $b;
}
echo addNumbers(5, "5 days");
// since strict is enabled and "5 days" is not an integer, an error will be thrown
?>
```

- **PHP Default Argument Value**

```php
<?php 
declare(strict_types=1); // strict requirement

function setHeight(int $minheight = 50) {
  echo "The height is : $minheight <br>";
}

setHeight(350);
setHeight(); // will use the default value of 50
setHeight(135);
setHeight(80);
?>
```

- **PHP Functions - Returning Values**
  - To let a function return a value, use the `return` statement:

```php
<?php 
declare(strict_types=1); // strict requirement

function sum(int $x, int $y) {
  $z = $x + $y;
  return $z;
}

echo "5 + 10 = " . sum(5, 10) . "<br>";
echo "7 + 13 = " . sum(7, 13) . "<br>";
echo "2 + 4 = " . sum(2, 4);
?>
```

- **PHP Return Type Declarations**
  - PHP 7 also supports Type Declarations for the return statement. 
  - Like with the type declaration for function arguments, by enabling the strict requirement, it will throw a "Fatal Error" on a type mismatch.
  - To declare a type for the function return, add a colon ( : ) and the type right before the opening curly ( { )bracket when declaring the function. 
  - You can specify a different return type, than the argument types, but make sure the return is the correct type.

```php
<?php 
declare(strict_types=1); // strict requirement

function addNumbers(float $a, float $b) : int {
  return (int)($a + $b);
}

echo addNumbers(1.2, 5.2);
?>
```

- **Passing Arguments by Reference**
  - In PHP, arguments are usually passed by value, which means that a copy of the value is used in the function and the variable that was passed into the function cannot be changed.
  - When a function argument is passed by reference, changes to the argument also change the variable that was passed in. 
  - To turn a function argument into a reference, the & operator is used.

```php
<?php
function add_five($value) {
  echo "Value is " . $value += 5;
}

$num = 2;
add_five($num);
echo "<br>";
echo "Num is $num";


function add_six(&$value) {
  echo "Value is " . $value += 6;
}

$num = 2;
add_five($num);
echo "<br>";
echo "Num is $num";
?>
```        

## PHP Strings

- A string is a sequence of characters, like "Hello world!".
- Some commonly used functions to manipulate strings are as follows:

  - **strlen() function**
    - The PHP `strlen()` function returns the length of a string.
    - `echo strlen("Hello world!"); // outputs 12`
  - **str_word_count() function**
    - The PHP `str_word_count()` function counts the number of words in a string.
    - `echo str_word_count("Hello world!"); // outputs 2`
  - **strrev() function**
    - The PHP `strrev()` function reverses a string.
    - `echo strrev("Hello world!"); // outputs !dlrow olleH`
  - **strpos() function**
    - The PHP `strpos()` function searches for a specific text within a string. If a match is found, the function returns the character position of the first match. If no match is found, it will return FALSE.
    - **Tip:** The first character position in a string is 0 (not 1).
    - `echo strpos("Hello world!", "world"); // outputs 6`
  - **str_replace() function**
    - The PHP `str_replace()` function replaces some characters with some other characters in a string.
    - `echo str_replace("world", "Dolly", "Hello world!"); // outputs Hello Dolly!`
  - **Complete PHP String Functions**
    - https://www.w3schools.com/php/php_ref_string.asp


## PHP Numbers

- PHP provides automatic data type conversion.
- So, if you assign an integer value to a variable, the type of that variable will automatically be an integer. 
- Then, if you assign a string to the same variable, the type will change to a string.
- This automatic conversion can sometimes break your code.
- **PHP Integers**
  - 2, 256, -256, 10358, -179567 are all integers.
  - An integer is a number without any decimal part.
  - An integer data type is a non-decimal number 
    - `between -2147483648 and 2147483647 in 32 bit systems` 
    - `between -9223372036854775808 and 9223372036854775807 in 64 bit systems`
    - A value greater (or lower) than this, will be stored as float, because it exceeds the limit of an integer.
  - Another important thing to know is that even if 4 * 2.5 is 10, the result is stored as float, because one of the operands is a float (2.5).
  - Rules for Integers:
    - An integer must have at least one digit.
    - An integer must NOT have a decimal point.
    - An integer can be either positive or negative.
    - Integers can be specified in three formats: decimal (10-based), hexadecimal (16-based - prefixed with 0x) or octal (8-based - prefixed with 0).
  - PHP has the following predefined constants for integers:
    - `PHP_INT_MAX` - The largest integer supported
    - `PHP_INT_MIN` - The smallest integer supported
    - `PHP_INT_SIZE` - The size of an integer in bytes
  - PHP has the following functions to check if the type of a variable is integer:
    - `is_int()`
    - `is_integer()` - alias of `is_int()`
    - `is_long()` - alias of `is_int()`

```php
<?php
$x = 5985;
var_dump(is_int($x));

$x = 59.85;
var_dump(is_int($x));
?>
```
- **PHP Floats**
  - A float is a number with a decimal point or a number in exponential form.
  - 2.0, 256.4, 10.358, 7.64E+5, 5.56E-5 are all floats.
  - The float data type can commonly store a value up to 1.7976931348623E+308 (platform dependent), and have a maximum precision of 14 digits.
  - PHP has the following predefined constants for floats (from PHP 7.2):
    - `PHP_FLOAT_MAX` - The largest representable floating point number
    - `PHP_FLOAT_MIN` - The smallest representable positive floating point number
    - `PHP_FLOAT_DIG` - The number of decimal digits that can be rounded into a float and back without precision loss
    - `PHP_FLOAT_EPSILON` - The smallest representable positive number x, so that x + 1.0 != 1.0
  - PHP has the following functions to check if the type of a variable is float:
    - `is_float()`
    - `is_double()` - alias of `is_float()`

```php
<?php
$x = 10.365;
var_dump(is_float($x));
?>
```

- **PHP Infinity**
- A numeric value that is larger than `PHP_FLOAT_MAX` is considered infinite.
- PHP has the following functions to check if a numeric value is finite or infinite:
  - `is_finite()`
  - `is_infinite()`
- However, the PHP var_dump() function returns the data type and value:

```php
<?php
$x = 1.9e411;
var_dump($x);
?>
```

- **PHP NAN**
- NaN stands for Not a Number.
- NaN is used for impossible mathematical operations.
- PHP has the following functions to check if a value is not a number:
  - `is_nan()`
- However, the PHP var_dump() function returns the data type and value:

```php
<?php
$x = acos(8);
var_dump($x);
?>
```