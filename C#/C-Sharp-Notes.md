# Find

- Stack Vs. Heap
- What is .NET Runtime
- Ilasm.exe Vs. Ildasm.exe

# C# Introduction

- Basic Structure of a C# Program
  - Console is a class and WriteLine is a function which is used to write messages on the console window
  - using System
    - This line tells the program that we are going to use the code which is present in the System namespace. A namespace is used to organize your code and is a collection of namespaces, classes, interfaces, structs, enums and delegates.
- What is a Namespace?
  - The namespace declaration, using System, indicates that you are using the System namespace.
  - A namespace is used to organize your code and is a collection of namespaces, classes, interfaces, structs, enums and delegates.
- Purpose of Main Method
  - It is the entry point into your application. This Main method tells where to start from and where to end the program execution.
  - Class: Any code that we are writing should be residing inside a class.

# Reading & Writing to Console

- C# is Case-Sensitive
- Reading from the Console
- Writing to the Console
  - Find => Write Vs. WriteLine Method
- 2 Ways to write to Console
  - Concatenation
  - Place Holder Syntax - Most Preferred
- Read about below Errors (Null – ReadLine)
  - https://stackoverflow.com/questions/70291276/converting-null-literal-for-console-readline-for-string-input

```console
using System;

namespace CSharpPractice
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Enter Your Name: ");
            String fname = Console.ReadLine() ?? "Nothing";
            Console.WriteLine($"First Name is {fname}");
            Console.WriteLine("First Name is {0}", fname);
        }
    }
}
```

# Built-In Types in C#

- Integral numeric types - C# reference | Microsoft Learn
- In C++ a boolean variable contains 0 or 1 but in C# it should be either true or false
- Unsigned start from 0 to ….. (positive number). Signed contains negative, zero, and positive values.
  - sbyte (-128 to 127) and byte (0 to 255) [8 bit integer i.e. 2<sup>8</sup> = 256 characters]
- All available types in C#
  - Boolean Type
  - Integral Types - sbyte, byte, short, ushort, int, uint, long, ulong, char
  - Floating Types - float and double
  - Decimal Types
  - String Types
  - Escape Sequences in C# (Backslash \)
    - It is used to perform escape sequence. Ex. “\”Manish\””
- Verbatim Literal
  - It is a string with an @ symbol prefix, as in @”C:\Manish\Dotnet”
  - It makes escape sequences translate as normal printable characters to enhance readability.
  - "D:\\\Kudvenkat\\\C#\\\Videos" -- Less Readable @"D:\Kudvenkat\C#\Videos" -- More Readable
  - https://learn.microsoft.com/en-us/cpp/c-language/escape-sequences?view=msvc-170

```console
using System;

namespace CSharpPractice
{
    class Program
    {
        static void Main(string[] args)
        {
            bool b = true;
            Console.WriteLine("Boolean Value {0}", b);

            sbyte var1 = -128;
            sbyte var2 = 127;
            byte var3 = 255;
            Console.WriteLine("sbyte {0}, sbyte {1}, byte {2}", var1, var2, var3);

            double d = 123.22322325;
            Console.WriteLine("Double d is {0}", d);

            Console.WriteLine("Sbyte Min Value {0} and Max Value {1}", sbyte.MinValue, sbyte.MaxValue);
            Console.WriteLine("Byte Min Value {0} and Max Value {1}", byte.MinValue, byte.MaxValue);
            Console.WriteLine("Integer Min Value {0} and Max Value {1}", int.MinValue, int.MaxValue);
        }
    }
}
```

```console
using System;

namespace CSharpPractice
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("One \n Two \n Three");
            Console.WriteLine("\"Manish\"");
            Console.WriteLine("C:\\Manish\\Dotnet");
            Console.WriteLine(@"'Manish'");
            Console.WriteLine(@"c:\xampp\sagar\sistec");
        }
    }
}
```

# Common Operators

```console
using System;

namespace CSharpPractice
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1.Assignment Operator =
            // 2.Arithmetic Operators + -*  /  %
            // 3.Comparison Operators ==  !=  >  ≥  <  ≤
            // 4.Conditional Operators && ||
            // 5.Ternary Operator ?:
            // 6.Null Coalescing Operator ??

            int age = 18;
            Console.WriteLine(age >= 18 ? "Can Vote" : "Can't Vote");
        }
    }
}
```

# Types in C#

- Types
  - int, float, double, structs, enums etc.
  - Value Types are non-nullable. To make them nullable use ?
    - int i = 0 (i is non nullable, so we can’t set i = null)
    - int? j = null (j is nullable int, so j = null is legal)
- Reference Types
  - Interface, Class, Delegates, Arrays etc.
- String is a class
- Find - Value Vs. Reference Types.
- Default value of a reference type is Null and Default value of a value type is some form of 0

# Nullable Types in C#

- Nullable Types
  - It bridges the differences between C# Types and Database Types. Database doesn’t have concept of value and reference types. We can store null for any datatype in the database. Earlier we used to perform nullable conversions for the database. But now we don’t need to.
  - Use case: If the user gets asked if he is a major. He probably answers yes or no. What if he doesn’t answer. What value would we store in the database.
- Null Coalescing Operator ??
- Ways of storing Nullable Variable’s Value to Non-Nullable Variable
- Find
  - null Vs. undefined Vs. “”
  - Default value for every value and reference types (Ex. integer, float, Class, array etc.) in C#

```console
using System;

namespace CSharpPractice
{
    class Program
    {
        static void Main(string[] args)
        {
            /* Nullable Types ? + Null Coalescing Operator ?? */
            int? i = null;
            int j = i ?? 0;
            Console.WriteLine($"I value is {i} and J value is {j}");

            int? k = 5;
            int l = k ?? 0;
            Console.WriteLine($"K value is {k} and L value is {l}");

            // Long way without using Null Coalescing Operator
            int? ticketsOnSale = null;
            int availableTickets = 0;

            if (ticketsOnSale == null)
            {
                availableTickets = 0;
            }
            else
            {
                // Here we have to assign a nullable variable's value to non nullable variable
                // If we try to accomplish this, it gives the following error:
                // Error: Cannot implicitly convert type int? to int.
                // availableTickets = ticketsOnSale;

                // 1st Solution : Type casting from int? to int
                // availableTickets = (int)ticketsOnSale;

                // 2nd Solution : Using Value Property
                availableTickets = ticketsOnSale.Value;
            }

            Console.WriteLine("Available Tickets = {0}", availableTickets);
        }
    }
}
```

# Datatype Conversions

- Implicit Conversions
  - When we convert small datatype to bigger datatype, there isn’t any loss of information.
  - There isn’t going to be any exception as well.
  - Ex. int to float (No loss of information and no exception thrown)
- Explicit Conversions
  - When converting a float to an int, we loose the fractional part and also a possibility of overthrow exception. Hence, in this case an explicit conversion is required. For explicit conversion we can use the typecast operator or the convert class in C#.
  - Difference between typecast operator and convert class is the typecast operator doesn’t throw an overflow exception if it can’t handle the value whereas Convert class throws an overflow exception if the value is too big
- Difference between Parse() and TryParse()
  - If the number is in a string format you have 2 options - Parse() and TryParse()
  - Parse() method throws an exception if it cannot parse the value, whereas TryParse() returns a bool indicating whether it succeeded or failed.
  - Use Parse() if you are sure the value will be valid, otherwise use TryParse()

```console
using System;

namespace CSharpPractice
{
    class Program
    {
        static void Main(string[] args)
        {
            int i = 100;
            float f = i;
            Console.WriteLine("Implicit Conversion from int to float = {0}", f);

            // As j value is too big to handle for (int) and Convert class.
            // Convert class gives overthrow exception
            //float j = 12565232656232363.23F;
            //int k = (int)j;
            //int k = Convert.ToInt32(j);

            float j = 125463.23F;
            int k = (int)j;
            int l = Convert.ToInt32(j);
            Console.WriteLine("Explicit Conversion from float to int = {0} & {1}", k, l);

            //Convert String to Integer : Parse Method vs. TryParse() Method
            //string numValue = "550tg";
            string numValue = "550";
            Console.WriteLine("Parse Method {0}", int.Parse(numValue));

            //string numValue2 = "550";
            string numValue2 = "550TG";
            int result;
            bool value = int.TryParse(numValue2, out result);
            Console.WriteLine("Try Parse = {0}", value ? result : 0);
        }
    }
}
```

# Arrays

- It’s a collection of items of similar datatype
- Pros: Strongly typed
- We can’t increase the size of an array once it’s initialized. Have to rely on integral indices to store or retrieve items from the array. (IndexOutOfRangeException)

```console
using System;

namespace CSharpPractice
{
    class Program
    {
        static void Main(string[] args)
        {
            int[] numbers = new int[5];
            numbers[0] = 1;
            numbers[1] = 2;
            numbers[2] = 3;
            numbers[3] = 4;
            numbers[4] = 5;
            Console.WriteLine(numbers);        // System.Int32[]
            Console.WriteLine(numbers[1]);     // 2

            string[] students = { "Manish", "Sanjay", "Rahul" };
            Console.WriteLine(students[1]);
            Console.WriteLine(students[students.Length - 1]);
            Console.WriteLine(students[^1]);
            Console.WriteLine(students[^2]);
        }
    }
}
```

# Comments

- Single Line Comments - //
- Multi Line Comments - /\* \*/
- Introduction to XML Documentation Comments - ///
- Comments are basically used to document what the program does and what specific blocks or lines of code do. C# compiler ignores comments.
- Don’t try to comment every line of code. Use comments only for blocks or lines of code that are difficult to understand.
- To Comment and Uncomment, there are 2 ways
  - Use the designer
  - To Comment : Keyboard Shortcut : Ctrl+K, Ctrl+C
  - To Uncomment : Keyboard Shortcut : Ctrl+K, Ctrl+U

# Conditional Statements

- if statement
- if else statement
- if else if else statement
- Difference between && and &
  - && - if it gets the first condition ‘false’, it doesn’t even bother to check the next condition. (Faster).
  - & - even if it gets the first condition ‘false’, it checks all the conditions. (Slower)
- Difference between || and |
  - || - if it gets the first condition ‘true’, it doesn’t even bother to check the next condition. (Faster).
  - | - even if it gets the first condition ‘true’, it checks all the conditions. (Slower)
- && and || are short circuit operators - Give performance boost. Don’t bother to check the entire expression if the first condition is true as per them.

# Switch statement

- Multiple if else statement can be replaced with a switch statement
- Used with break keyword. If break statement is used inside a switch statement, the control will leave the switch statement.
- goto statement - You can either jump to another case statement, or to a specific label. Using goto statement is bad programming style. We should avoid goto by all means.
- Case statements, with no code in-between, creates a single case for multiple values. A case without any code will automatically fall through to the next case.

```console
using System;

namespace CSharpPractice
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Enter a Numbers : 1, 2 or 3 only");
            int target = 0;
            bool condition = int.TryParse(Console.ReadLine(), out target);

            if (condition)
            {
                switch (target)
                {
                    case 1:
                        Console.WriteLine("One");
                        break;
                    case 2:
                        Console.WriteLine("Two");
                        break;
                    case 3:
                        Console.WriteLine("Three");
                        break;
                    default:
                        Console.WriteLine("Invalid Value");
                        break;
                }
            }
            else
            {
                Console.WriteLine("Please enter a number only");
            }
        }
    }
}
```

# Loops

- while loop
  - It checks the condition first.
  - If the condition is true, the code with in the loop executed.
  - This process is repeated as long as the condition evaluates to true.
- do-while loop
  - A do-while loop checks its condition at the end of the loop.
  - This guarantees the do-while loop to execute at least one time.
  - do-while loops are used to present a menu to the user.
- for loop
  - A for loop is very similar to while loop. In a while loop we do the initialization at one place, condition check at another place, and modifying the variable at another place, where as the for loop has all of these at one place.
- foreach loop
  - It is used to iterate through the items in a collection. For example, it can be used with arrays or collections such as ArrayList, HastTable and Generics.

```console
using System;

namespace CSharpPractice
{
    class Program
    {
        static void Main(string[] args)
        {
            int i = 1;
            while (i <= 5)
            {
                Console.WriteLine(i);
                i++;
            }

            int j = 1;
            do
            {
                Console.WriteLine(j);
                j++;
            } while (j <= 5);

            int[] numArray = { 1, 2, 3, 4, 5, 6 };
            for (int k = 0; k < numArray.Length; k++)
            {
                if (numArray[k] % 2 == 0)
                {
                    Console.WriteLine("{0} is even", numArray[k]);
                }
            }

            foreach (string letter in new string[] { "A", "B", "C" })
            {
                Console.WriteLine(letter);
            }

            foreach(var item in new int[] { 10, 20, 30, 40, 50}) {
                Console.WriteLine(item);
            }
        }
    }
}
```

# Methods

- Methods are also called as functions. These terms are used interchangeably. Extremely useful because they allow you to define your logic once, use it, at many places. Methods make the maintenance of your application easier.
- Structure of a method
  - Attributes
  - Access Modifiers
  - Return Type - It can be any valid data type or void.
  - Method Name - It can be any meaningful name.
  - Parameters - These are optional.
  - Method Body - Statements / Code with in the method block.
  - Example
  ```console
  [attributes]
  access-modifiers return-type method-name (parameters)
  {
    method body
  }
  ```
- Difference between static and instance methods
  - When a method declaration includes a static modifier, that method is said to be a static method. When no static modifier is present, the method is said to be an instance method.
  - Static method is invoked using the class name, where as an instance method is invoked using an instance of the class.
  - The difference between instance methods and static methods is that multiple instances of a class can be created (or instantiated) and each instance has its own separate method. However when a method is static, there are no instances of that method, and you can invoke only that one definition of the static method.

```console
using System;

class Methods
{
    // static method
    public static void MethodStatic()
    {
        Console.WriteLine("Static Method");
    }

    // instance method
    public void MethodInstance()
    {
        Console.WriteLine("Instance Method");
    }

    public void PrintEvenNumbers(int UserTarget)
    {
        for (int i = 2; i <= UserTarget; i += 2)
        {
            Console.WriteLine(i);
        }
    }

    public int AddTwoNumbers(int one, int two)
    {
        return one + two;
    }
}

namespace CSharpPractice
{
    class Program
    {
        static void Main(string[] args)
        {
            Methods obj = new Methods();
            Methods.MethodStatic();
            obj.MethodInstance();
            obj.PrintEvenNumbers(30);
            Console.WriteLine("Addition is {0}", obj.AddTwoNumbers(5, 10));
        }
    }
}
```

# Methods Parameters

- 4 Types of Method Parameters
  - Value Parameters
    - Creates a copy of the parameter passed, so modifications does not affect each other.
    - I and J are pointing to different memory locations. Operations on one variable will not affect the value of the other variable.
  - Reference Parameters
    - The ref keyword on a method parameter causes a method to refer to the same variable and that was passed into the method. Any changes made to the parameter in the method will be reflected in that variable when control passes back to the calling method.
    - I and J are pointing to the same memory location. Operations on one variable will affect the value of the other variable. It must be done with the ‘ref’ keyword.
  - Out Parameters
    - Use when you want a method to return more than one value.
  - Parameter Arrays
    - The params keyword lets you specify a method parameter that takes a variable number of arguments. You can send a comma-separated list of arguments, or an array, or not arguments. Params keyword should be the last one in a method declaration, and only one params keyword is permitted in a method declaration. You can use params keyword if you want to make your arguments optional.
- Method Parameters Vs. Method Arguments
  - A parameter is a variable in a method definition. When a method is called or invoked, the arguments are the data you pass into the method's parameters.

```console
using System;

class MethodParameters
{
    public static int PassByValue(int num)
    {
        num = 101;
        return num;
    }

    public static int PassByReference(ref int num)
    {
        num = 101;
        return num;
    }

    public static void OutParam(int FN, int SN, out int total, out int product)
    {
        total = FN + SN;
        product = FN * SN;
    }

    public static void ParamsKeyword(params int[] Numbers)
    {
        Console.WriteLine("There are {0} elements", Numbers.Length);
        int Sum = 0;
        foreach (int i in Numbers)
        {
            Sum += i;
        }
        Console.WriteLine("Total of Array's Elements is {0}", Sum);
    }

    public static void ParamsKeywordShouldBeLast(int i, params int[] numArray)
    {
        Console.WriteLine("First Digit is {0} | Array Length is {1} | Last Element of Array is {2}", i, numArray.Length, numArray[numArray.Length - 1]);
    }
}

namespace CSharpPractice
{
    class Program
    {
        static void Main(string[] args)
        {
            // Method Parameters | PassByValue
            int i = 10;
            int j = MethodParameters.PassByValue(i);
            Console.WriteLine("i = {0} & j = {1}", i, j);

            // Method Parameters | PassByReference
            int x = 10;
            int y = MethodParameters.PassByReference(ref x);
            Console.WriteLine("x = {0} & y = {1}", x, y);

            // out Param (Return multiple statements)
            int total = 0;
            int product = 0;
            MethodParameters.OutParam(10, 20, out total, out product);
            Console.WriteLine("Total is {0} & Product is {1}", total, product);

            // params keyword | send multiple arguments either array or comma separated or empty
            int[] NumbersArray = { 10, 20, 30, 40, 50 };
            MethodParameters.ParamsKeyword(NumbersArray);
            MethodParameters.ParamsKeyword(100, 200, 300);
            MethodParameters.ParamsKeyword();

            // params keyword should be the last argument
            MethodParameters.ParamsKeywordShouldBeLast(10, new int[] { 15, 16, 17, 18 });
        }
    }
}
```

# Namespaces

- Namespace basics
  - Namespaces are used to organize your programs.
  - They also provide assistance in avoiding name clashes.
  - 2 Ways to avoid ambiguity reference between similar class names of different namespaces
    - First use fully qualified name. [Ex. ProjectA.InnerProjectA.PrintMeClass.printMe()]
    - Use aliases. Ex:
      - using PATA = ProjectA.InnerProjectA; using PATB = ProjectA.InnerProjectB;
      - PATA.PrintMeClass.printMe(); PATB.PrintMeClass.printMe();
  - Namespaces don’t correspond to file, directory or assembly names. They could be written in separate files and / or separate assemblies and still belong to the same namespace.
  - Namespace can be nested in two ways
    - Namespace inside the curly braces of other namespace
    - Namespace.Namespace on one single line
  - Namespace alias directives. Sometimes you may encounter a long namespace and wish to have it shorter. This could improve readability and still avoid name clashes with similarly named methods
- Using alias directive
  - Alias is used to resolve ambiguity name issue
  - If the namespace name is too long to write again and again
  - Until we hover the class, we don’t know which namespace this class has come from.
  - Some people like typing fully qualified name. Some like to hover to find which namespace did this class come from.
  - Use alias to avoid too much of typing and know in advance to which namespace this class belongs to.
- Different namespace members
  - Another namespace / Class / Interface / struct / enum / delegate
- Find? What is an Assembly Vs. Project

```console
using System;

/*
 * In order to use below class libraries you have to add their references in the CSharpPractice Project
 * Right Click on CSharpPractice Project => Add => Project References
 * Check both Class Libraries
 */

/*
 * What if we don't use fully qualified name instead we use using and alias directive on top of this page.
 * This results ambiguity error as both these libraries have same class and same method.
 * Error: PrintClass is an ambiguous reference between 'NamespaceA.TeamA.PrintClass' and 'NamespaceB.TeamB.PrintClass'
 * To solve this issue use alias directive   [Remove aliases on the top first to see this error]
 * PrintClass.PrintMe();
 */

/* Create Alias Here */
using PrintAliasA = NamespaceA.TeamA;
using PrintAliasB = NamespaceB.TeamB;

namespace CSharpPractice
{
    class Program
    {
        static void Main(string[] args)
        {
            /* Type fully qualified name */
            NamespaceA.TeamA.PrintClass.PrintMe();
            NamespaceB.TeamB.PrintClass.PrintMe();

            /* With Alias */
            PrintAliasA.PrintClass.PrintMe();
            PrintAliasB.PrintClass.PrintMe();
        }
    }
}

==> Create a project of type Class Assembly and name it NamespaceA.TeamA
using System;
namespace NamespaceA
{
    namespace TeamA
    {
        public class PrintClass
        {
            public static void PrintMe()
            {
                Console.WriteLine("Printing NamespaceA TeamA PrintClass PrintMe Method");
            }
        }
    }
}

==> Create a project of type Class Assembly and name it NamespaceB.TeamB
using System;
namespace NamespaceB.TeamB
{
    public class PrintClass
    {
        public static void PrintMe()
        {
            Console.WriteLine("Printing NamespaceB TeamB PrintClass PrintMe Method");
        }
    }
}
```

# Classes

- What is a class?
  - If you want to create complex custom types, then we can make use of classes.
  - A class consists of data and behaviour. Class data is represented by its fields and behaviour by its methods.
- Purpose of a class constructor?
  - Its purpose is to initialize the class fields. A class constructor is automatically called when an instance of a class is created.
  - Constructors do not have return values and always have the same name as the class.
  - Constructors are not mandatory. If we don’t provide a constructor, a default parameter less constructor is automatically provided.
  - Constructors can be overloaded by the number and type of parameters.
- Overloading class constructor?
- Understanding this keyword?
  - this keyword refers to the current object of the class.
- Destructors
  - Destructors have the same name as class with ~ (tilde) symbol in front of them.
  - They don’t take any parameters and don’t return any value.
  - Destructors are places where you could put your code to release any resources your class was holding during its lifetime.
  - They are normally called when the C# garbage collector decides to clean your object from memory.

```console
using System;

class ClassWithConstructor
{
    string _firstName;
    string _lastName;

    // Overload ClassWithConstructor Constructor with Default Values
    public ClassWithConstructor() : this("Nothing", "Nothing") { }

    public ClassWithConstructor(string FirstName, string LastName)
    {
        this._firstName = FirstName;
        this._lastName = LastName;
    }

    public void printFullName()
    {
        Console.WriteLine("First Name is {0} & Last Name is {1}", this._firstName, this._lastName);
    }

    // Destructor
    ~ClassWithConstructor() { }
}

namespace CSharpPractice
{
    class Program
    {
        static void Main(string[] args)
        {
            ClassWithConstructor C1 = new ClassWithConstructor();
            C1.printFullName();
            ClassWithConstructor C2 = new ClassWithConstructor("Manish", "Sajandasani");
            C2.printFullName();
        }
    }
}
```

# Static and Instance Class Members

- Difference between Static and Instance Members
  - Static Class Members
    - When a class member includes a static modifier, the member is called a static member. When no static modifier is present the member is called as non-static member or instance member.
    - Static members are invoked using class name, where as instance members are invoked using instances (objects) of the class.
    - There will be only one static field in the memory which will be accessed by the objects of the class. Static fields are not changed on the pair object basis.
  - Instance Class Members
    - An instance member belongs to specific instance (object) of a class. If I create 3 objects, I will have 3 sets of instance members in the memory, where as there will ever be only one copy of a static member, no matter how many instances of a class are created.
    - Note: class members = fields, methods, properties, events, indexers, constructors.
- Static Constructor
  - Static constructor is used to initialize static fields in a class.
  - You declare a static constructor by using the keyword static in front of the constructor’s name.
  - Static constructor is called only once, no matter how many instances you create.
  - Static constructor is called before instance constructors. Even before you refer to any public static fields of the class.
  - Access modifiers are not allowed on Static Constructors.
  - Don’t use public modifier in front of the static constructor’s name. It doesn’t make sense. You are never gonna be changing the working of a static constructor. So, let it be private by default.
- Find? When should we make certain members static?

```console
using System;

class StaticInstanceClassMembers
{
    public static float _PI;
    int _Radius;

    static StaticInstanceClassMembers()
    {
        Console.WriteLine("Static Constructor Called");
        StaticInstanceClassMembers._PI = 3.141F;
    }

    public StaticInstanceClassMembers(int Radius)
    {
        Console.WriteLine("Instance Constructor Called");
        this._Radius = Radius;
    }

    public void calculateCircleArea()
    {
        float _Area = StaticInstanceClassMembers._PI * _Radius * _Radius;
        Console.WriteLine("Area of Circle is {0}", _Area);
    }
}

namespace CSharpPractice
{
    class Program
    {
        static void Main(string[] args)
        {
            StaticInstanceClassMembers obj1 = new StaticInstanceClassMembers(5);
            obj1.calculateCircleArea();
            StaticInstanceClassMembers obj2 = new StaticInstanceClassMembers(6);
            obj2.calculateCircleArea();
            Console.WriteLine(StaticInstanceClassMembers._PI);
        }
    }
}
```

# Inheritance in C#

- Why and advantages Inheritance?
  - Inheritance is one of the pillars of object-oriented programming.
  - It allows code reuse.
  - Code reuse can reduce code time, code errors, and testing time.
  - Note: You will specify all the common fields, properties, methods in the base class, which allows reusability. In the derived class you will only have fields, properties and methods, that are specific to them.
- Inheritance Syntax & Concepts
  - Derived/Child Class inherits Base/Parent Class.
  - C# supports only Single Class Inheritance.
  - C# supports Multilevel Inheritance & Multiple Interface Inheritance.
  - Child class is a specialization of base class.
  - Base classes are automatically instantiated before derived classes. This means you can access data members of the parent class with the instance of the child class.
  - Parent class constructor executes before Child class constructor.

```console
using System;

class InheritanceEmployee
{
    public string FirstName;
    public string LastName;

    public InheritanceEmployee()
    {
        Console.WriteLine("Employee Class Constructor");
    }

    public InheritanceEmployee(string Message)
    {
        Console.WriteLine("Parent Class Message = {0}", Message);
    }

    public void PrintFullName()
    {
        Console.WriteLine("{0} {1}", this.FirstName, this.LastName);
        Console.WriteLine("\n");
    }
}

class FullTimeEmployee : InheritanceEmployee
{
    public float YearlySalary;

    public FullTimeEmployee()
    {
        Console.WriteLine("Full Time Employee Class Constructor");
    }

    public void printSalary()
    {
        Console.WriteLine("Full Time Employee Salary is {0}", this.YearlySalary);
        Console.WriteLine("\n");
    }
}

class PartTimeEmployee : InheritanceEmployee
{
    public float HourlyRate;

    public PartTimeEmployee()
    {
        Console.WriteLine("Part Time Employee Class Constructor");
    }

    public void printSalary()
    {
        Console.WriteLine("Part Time Employee Salary is {0}", this.HourlyRate * 8 * 365);
        Console.WriteLine("\n");
    }
}

class ChildClass : InheritanceEmployee
{
    public ChildClass()
    {
        Console.WriteLine("Child Class Constructor");
    }

    public ChildClass(string Message) : base(Message)
    {
        Console.WriteLine("Child Class Message");
    }
}

namespace CSharpPractice
{
    class Program
    {
        static void Main(string[] args)
        {
            FullTimeEmployee FTE = new FullTimeEmployee();
            FTE.FirstName = "Manish";
            FTE.LastName = "Sajandasani";
            FTE.YearlySalary = 600000.00F;
            FTE.PrintFullName();
            FTE.printSalary();

            PartTimeEmployee PTE = new PartTimeEmployee();
            PTE.FirstName = "Manish";
            PTE.LastName = "Sajandasani";
            PTE.HourlyRate = 200.00F;
            PTE.PrintFullName();
            PTE.printSalary();

            ChildClass CC1 = new ChildClass();
            ChildClass CC2 = new ChildClass("Hum to Paagal Hai Bhai");
        }
    }
}
```

# Method Hiding or Method Overriding in C#

- Method Hiding Concept
  - Use the new keyword to hide a parent class member. You will get a compiler warning, if you miss the new keyword.
- Different ways to invoke a hidden parent class member from derived class
  - Use base keyword
  - Cast child type to parent type and invoke the hidden member
    - ((MethodHidingEmployee)pte).printFullName();
  - A parent class reference variable can point to a child class object but vice-versa is not true
    ParentClass PC = new ChildClass()
    PC.HiddenMethod()

```console
using System;

class MethodHidingEmployee
{
    public string _FName;
    public string _LName;

    public void printFullName()
    {
        Console.WriteLine(this._FName + " " + this._LName + " - From Parent Class");
    }
}

class FTimeEmployee : MethodHidingEmployee
{

}

class PTimeEmployee : MethodHidingEmployee
{
    // This is called Method Hiding / Method Overriding
    // Here new is the keyword which is used to hide the base class method
    public new void printFullName()
    {
        //// In case we wish to call base class method, use base keyword
        //base.printFullName();
        Console.WriteLine(this._FName + " " + this._LName + " - Contractor");
    }
}

namespace CSharpPractice
{
    class Program
    {
        static void Main(string[] args)
        {
            FTimeEmployee fte = new FTimeEmployee();
            fte._FName = "Anil";
            fte._LName = "Kapoor";
            fte.printFullName();

            PTimeEmployee pte = new PTimeEmployee();
            pte._FName = "Salman";
            pte._LName = "Khan";
            pte.printFullName();

            //We can use typecast operator to call parent class method without using base keyword in the child's class method
            ((MethodHidingEmployee)pte).printFullName();

            //Another Way of calling the parent's class method with the child's class object is to store the child's class object into the parent's class reference
            // A parent class reference variable can point to a child class object but vice-versa is not true
            MethodHidingEmployee obj = new PTimeEmployee();
            obj._FName = "Satish";
            obj._LName = "Kaushik";
            obj.printFullName();
        }
    }
}
```

# Polymorphism

- If you hide parent class’s method intentionally in the child class use ‘new’ keyword
  - PartTimeEmployee.PrintFullName() hides inherited member Employee.PrintFullName(). Use the new keyword if hiding was intended.
- If you wish to override the definition of the parent class method in the child class:
  - Use override keyword with the child class method
  - Use virtual keyword with the parent class method
  - The virtual keyword indicates the child classes that they can override the method if they wish so.
  - If they don’t override, the parent class method implementation will be called
  - Even though you use parent class reference variable, if you have overridden the methods using override keyword, it would invoke the child classes method implementation
- Polymorphism
  - One of the primary pillars of object-oriented programming.
  - It basically enables you to invoke derived class methods through a base class reference variable at run time.
  - In the base class the method is declared virtual, and in the derived class we override the same method.
  - The virtual keyword indicates the method can be overridden in any derived class.

```console
using System;

class CustomerPolymorphism
{
    public string _FName = "Manish";
    public string _LName = "Sajandasani";

    public virtual void printFullName()
    {
        Console.WriteLine(this._FName + " " + this._LName);
    }
}

class FullTimeCustomer : CustomerPolymorphism
{
    public override void printFullName()
    {
        Console.WriteLine(this._FName + " " + this._LName + " - Full Time");
    }
}

class PartTimeCustomer : CustomerPolymorphism
{
    public override void printFullName()
    {
        Console.WriteLine(this._FName + " " + this._LName + " - Part Time");
    }
}

class TemporaryTimeCustomer : CustomerPolymorphism
{
    public override void printFullName()
    {
        Console.WriteLine(this._FName + " " + this._LName + " - Temporary Time");
    }
}

namespace CSharpPractice
{
    class Program
    {
        static void Main(string[] args)
        {
            /* Create CustomerPolymorphism Type Array */
            CustomerPolymorphism[] customers = new CustomerPolymorphism[4];

            /* To each array element assign different type of object */
            customers[0] = new CustomerPolymorphism();
            customers[1] = new FullTimeCustomer();
            customers[2] = new PartTimeCustomer();
            customers[3] = new TemporaryTimeCustomer();

            /* Loop through all array elements and invoke the child/parent class method */
            foreach (CustomerPolymorphism cp in customers)
            {
                cp.printFullName();
            }
        }
    }
}
```

# Difference between Method Overriding and Method Hiding

- In Method Overriding a base class reference variable pointing to a child class object, will invoke the overriden method in the Child Class
- In Method Overriding
  - Use virtual keyword with the parent class method
  - Use override keyword with the child class method
- In Method Hiding a base class reference variable pointing to a child class object, will invoke the hidden method in the Parent Class
- In Method Hiding
  - Use virtual keyword with the parent class method
  - Use new keyword with the child class method

```console
using System;

public class MethodOverrideHidingParentClass
{
    public virtual void Print()
    {
        Console.WriteLine("Print Method - Parent Class");
    }
}

public class OverrideChildClass : MethodOverrideHidingParentClass
{
    public override void Print()
    {
        Console.WriteLine("Print Method - Child Class 1 (Override)");
    }
}

public class HidingChildClass : MethodOverrideHidingParentClass
{
    public new void Print()
    {
        Console.WriteLine("Print Method - Child Class 2 (Hide)");
    }
}

namespace CSharpPractice
{
    class Program
    {
        static void Main(string[] args)
        {
            /* Difference Between Method Overriding and Method Hiding */
            MethodOverrideHidingParentClass pcObj1 = new OverrideChildClass();
            pcObj1.Print();

            MethodOverrideHidingParentClass pcObj2 = new HidingChildClass();
            pcObj2.Print();
        }
    }
}
```

# Method Overloading

- Function overloading and Method overloading terms are used interchangeably.
- Method overloading allows a class to have multiple methods with the same name, but, with a
  different signature. So, in C# functions can be overloaded based on the number, types (int, float, etc.) and kind (value, reference or out) of parameters.
- The signature of a method consists of the name of the method and the type, kind (value,
  reference, or output) and the number of its formal parameters. The signature of a method does
  not include the return type and the params modifier. So, it is not possible to overload a function, just based on the return type or params modifier.
- For Method Parameters, watch Part 17

```console
using System;

namespace CSharpPractice
{
    class Program
    {
        static void Main(string[] args)
        {
            int total = 0;
            int product = 0;

            Add(10, 20, 30);
            Add(10.3f, 20.6f, 30);
            Add(40, 80.6f);
            Add(10, 20, out total, out product);
            Console.WriteLine("Total = {0}, Product = {1}", total, product);

            Add(1, 2, new int[] { 3, 4, 5 });
            Add(10, 20, 30, 40, 50);
            Add(10, 20);
        }

        public static void Add(int FN, int SN, int TN)
        {
            Console.WriteLine("Sum = {0}", FN + SN + TN);
        }

        public static void Add(float FN, float SN, float TN)
        {
            Console.WriteLine("Sum = {0}", FN + SN + TN);
        }

        public static void Add(int FN, float SN)
        {
            Console.WriteLine("Sum = {0}", FN + SN);
        }

        public static void Add(int FN, int SN, out int total, out int product)
        {
            total = FN + SN;
            product = FN * SN;
        }

        public static void Add(int FN, int SN, params int[] TN)
        {
            int sum = FN + SN;
            foreach (int i in TN)
            {
                sum += i;
            }
            Console.WriteLine("TN Length = {0} and Sum = {1}", TN.Length, sum);
        }

        /* Wrong - Not Possible - Here we have just changed the return type */
        //public static int Add(int FN, int SN, int TN)
        //{
        //    Console.WriteLine("Sum = {0}", FN + SN + TN);
        //}

        /* Wrong - Not Possible - Here we have just removed the params keyword */
        //public static void Add(int FN, int SN, int[] TN)
        //{

        //}
    }
}
```

# Properties

- Why Properties
  - Marking the class fields public and exposing to the external world is bad, as you will not have control over what gets assigned and returned.
  - Problems with Public Fields
    1. ID should always be non negative number.
    2. Name cannot be set to NULL
    3. If Student Name is missing "No Name" should be returned
    4. PassingMarks should be read only

```console
public class Student {
    public int ID;
    public string Name;
    public int PassingMarks;
}

public class Program {
    public static void Main() {
        Student s1 = new Student();
        s1.ID = -101;
        s1.Name = null;
        s1.PassingMarks = -200;
    }
}
```

- Getter & Setter Methods
  - Programming languages that does not have properties use getter and setter methods to encapsulate and protect fields.
  - In this example we use the SetId(int Id) and GetId() methods to encapsulate \_id class field.
  - As a result, we have better control on what gets assigned and returned from the \_id field.
  - Note: Encapsulation is one of the primary pillars of object oriented programming.

```console
using System;

public class Student
{
    private int _id;
    private string _Name;
    private int _PassMark = 35;

    public void SetName(string Name)
    {
        if (string.IsNullOrEmpty(Name))
        {
            throw new Exception("Name cannot be null or empty");
        }
        this._Name = Name;
    }

    public string GetName()
    {
        return (string.IsNullOrEmpty(this._Name)) ? "No Name" : this._Name;
    }

    public void SetId(int Id)
    {
        if (Id < 0)
        {
            throw new Exception("Student ID should be greater than zero");
        }
        this._id = Id;
    }

    public int GetId()
    {
        return this._id;
    }

    public int GetPassMark()
    {
        return this._PassMark;
    }
}

namespace CSharpPractice
{
    class Program
    {
        static void Main(string[] args)
        {
            Student s1 = new Student();
            s1.SetId(200);
            s1.SetName("Manish");
            Console.WriteLine("Student ID = {0}", s1.GetId());
            Console.WriteLine("Student Name = {0}", s1.GetName());
        }
    }
}
```

- In C# to encapsulate and protect fields we use properties
  - We use get and set accessors to implement properties
  - A property with both get and set accessor is a Read/Write property
  - A property with only get accessor is a Read only property
  - A property with only set accessor is a Write only property
  - Note: The advantage of properties over traditional Get() and Set() methods is that, you can access them as if they were public fields.
  - Auto-Implemented Properties
    - If there is no additional logic in the property accessors, then we can make use of auto-implemented properties introduced in C# 3.0.
    - Auto-implemented properties reduce the amount of code that we have to write.
    - When you use auto-implemented properties, the compiler creates a private, anonymous field that can only be accessed through the property's get and set accessors.

```console
using System;

public class Student
{
    private int _id;
    private string? _Name;
    private readonly int _PassMark = 35;

    // Auto-Implemented Properties
    public string? City { get; set; }
    public string? Email { get; set; }

    public int Id
    {
        set
        {
            if (value < 0)
            {
                throw new Exception("Student ID should be greater than zero");
            }
            this._id = value;
        }

        get
        {
            return this._id;
        }
    }

    public string Name
    {
        set
        {
            if (string.IsNullOrEmpty(value))
            {
                throw new Exception("Name cannot be null or empty");
            }
            this._Name = value;
        }

        get
        {
            return (string.IsNullOrEmpty(this._Name)) ? "No Name" : this._Name;
        }
    }

    public int PassMark
    {
        get
        {
            return this._PassMark;
        }
    }
}

namespace CSharpPractice
{
    class Program
    {
        static void Main(string[] args)
        {
            Student s1 = new Student();
            s1.Id = 200;
            s1.Name = "Manish";
            s1.City = "Bhopal";
            s1.Email = "msajandasani@gmail.com";
            Console.WriteLine("Student ID = {0}", s1.Id);
            Console.WriteLine("Student Name = {0}", s1.Name);
            Console.WriteLine("Student PassMark = {0}", s1.PassMark);
            Console.WriteLine("Student City = {0}", s1.City);
            Console.WriteLine("Student Email = {0}", s1.Email);
        }
    }
}
```

# Structs

- Just like classes structs can have
  - Private Fields
  - Public Properties
  - Constructors
  - Methods
- Object Intializer Syntax, introduces in C# 3.0 can be used to initialize either a struct or a class.
- Note: There are several differences between classes and structs

```console
using System;

namespace CSharpPractice
{
    public struct Customer
    {
        private int _id;
        private string _name;

        public Customer(int Id, string Name) {
            this._id = Id;
            this._name = Name;
        }

        public int ID {
            get
            {
                return this._id;
            }

            set
            {
                this._id = value;
            }
        }
        public string Name {
            get
            {
                return this._name;
            }

            set
            {
                this._name = value;
            }
        }

        public void PrintCustomer() {
            Console.WriteLine("Customer Name is {0} and ID is {1}", this._name, this._id);
        }
    }

    class Program
    {
        static void Main(string[] args)
        {
            /* Initialize Field Values with Constructor */
            Customer C1 = new Customer(101, "Manish");
            C1.PrintCustomer();

            /* Initialize Field Values with Properties */
            Customer C2 = new Customer();
            C2.ID = 102;
            C2.Name = "Sanjay";
            C2.PrintCustomer();

            /* Initialize Field Values with Object Intializer Syntax (C# 3.0) */
            Customer C3 = new Customer
            {
                ID = 103,
                Name = "Rahul"
            };
            C3.PrintCustomer();
        }
    }
}
```

# Differences between Classes and Structures

- We understood that structs are very similar to classes. We use struct keyword to create a struct.
- Just like classes structs can have fields, properties, constructors and methods.
- However, there are several differences between classes and structs.
- Classes Vs Structs
  - A struct is a value type where as a class is a reference type.
  - All the differences that are applicable to value types and reference type are also applicable to classes and structs.
  - Structs are stored on stack, where as classes are stored on the heap.
  - Value types hold their value in memory where they are declared, but reference types hold a reference to an object in memory.
  - Value types are destroyed immediately after the scope is lost where as for reference types only the reference variable is destroyed after the scope is lost. The object is later destroyed by garbage collector.
  - When you copy a struct into another struct, a new copy of that struct gets created and modifications on one struct will not affect the values contained by the other struct.
  - When you copy a class into another class, we only get a copy of the reference variable. Both the
    reference variables point to the same object on the heap. So, operations on one variable will affect the values contained by the other reference variable.
  - When we create an object, the object reference variable stores on the stack and the object itself stores on the heap. The object reference variable points to the object. Ex. i = 10, j = 20, C1 will be stored on the stack and C1.ID = 101, C1.Name = "Mark" will be stored on the heap.
  - Structs can't have destructors, but classes can have.
  - Structs cannot have explicit parameter less constructor where as a class can.
  - Structs can't inherit from another class where as a class can, Both structs and classes can inherit from an interface.
  - Examples of structs in the .NET Framework- int (System-Int32), double(System.Double) etc.
  - Note 1: A class or a struct cannot inherit from another struct. Struct are sealed types.
  - Note 2: How do you prevent a class from being inherited? Or What is the significance of sealed keyword?
- Remember:
  - int is just an alias of structure System.Int32
