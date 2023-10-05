# Default Directory Structure

- Connected Services
  - No service dependencies discovered
- Dependencies
  - Analyzers
  - Frameworks
    - Microsoft.AspNetCore.App
    - Microsoft.NETCore.App
- Properties
  - launchSettings.json
- wwwroot
  - css
  - js
  - lib
  - favicon.ico
- Controllers
  - HomeController.cs
- Models
  - ErrorViewModel.cs
- Views
  - Home
    - Index.cshtml
    - Privacy.cshtml
  - Shared
    - \_Layout.cshtml
    - \_ValidationScriptsPartial.cshtml
    - Error.cshtml
  - \_ViewImports.cshtml
  - \_ViewStart.cshtml
- appsettings.json
- Program.cs

# Find

- Learn about every file and folder present in the AspNetCore Web Application
- What is ILogger
- What is ILogger\<HomeController>
- What is IActionResult
- What is IEnumerable or IEnumerator (All types of Interfaces in C# and ASP.NET Core)
- Difference between .NET Core and .NET Framework
- Difference between ASP.NET and ASP.NET Core
- What is MVC in ASP.NET Core MVC
- Create ASP.NET Core MVC Web APP in Visual Studio 2022
- What are Services in ASP.NET Core Web App
- What are all important middlewares in ASP.NET Core Web App
- Concept of Endpoints, Async and Await, Request Delegates in Map, MapGet, MapPost, MapPut, MapDelete
- Route Constraints {id:int?}
-

```console
private readonly ILogger<HomeController> _logger;
public HomeController(ILogger<HomeController> logger)
{
    _logger = logger;
}

public IActionResult Index()
{
    return View();
}
```

# launchSettings.json

- Present in Properties folder. Contains settings that control how your web app is going to start on your development machine. These settings are going to be used when we run .NET core application either from Visual Studio or by using .NET Core CLI.
- It is only used within the Local Development Machine not in the Production Server.
- Settings for IIS Express

```console
"IIS Express": {
  "commandName": "IISExpress",
  "launchBrowser": true,
  "environmentVariables": {
    "ASPNETCORE_ENVIRONMENT": "Development"
  }
}
```

- Settings for Kestrel Web Server

```console
"AspNetCoreMVC6": {
  "commandName": "Project",
  "dotnetRunMessages": true,
  "launchBrowser": true,
  "applicationUrl": "https://localhost:7051;http://localhost:5030",
  "environmentVariables": {
    "ASPNETCORE_ENVIRONMENT": "Development"
  }
},
```

# appsettings.json

- If you have worked with previous versions of ASP.NET application, then you know the importance of the web.config file
- In previous version we generally used to store the applicaton configuration settings such as database connection strings, any application scope global variables and many more within the web.config file
- When we create an ASP.NET Core Web Application with an Empty Project Template or Razor Pages or MVC Template or Web API Template, then the Visual Studio automatically creates the appsettings.json file for us.
- The appsettings.json is an application configuration file used to store configuration settings such as database connection strings, any application scope global variables, etc.

# Program.cs

- It is the very first file which runs

# Middleware

- A middleware is nothing but a component (class) which is executed on every request in ASP.NET Core Application
- There is a HTTP Request Pipeline which is present between the client (browsers) and the web application. This request pipeline contains all the middlewares.
- Every request has to go through all these middlewares. We have to mention all the built-in and custom middlewares in the Program.cs file.
- Middleware controls how our application would respond to HTTP requests.
- Middlewares are software components that are assembled into an application pipeline to handle requests and responses.
- It can also control how our application responds when there is an error.
- It is a key piece in how we authenticate and authorize a user to perform specific actions.
- Each piece of middleware in ASP.NET Core is an object, and each piece has a very specific, focused, and limited role.
- Orders of middlewares is very important.
- We can create our own custom middlewares. For this we use methods. We can use either Run() or Use() method. Run method doesn't have the concept of next. So it doesn't execute the next middleware in the order.

```console
==> Program.cs File
app.Use(async (context, next) =>
{
    await context.Response.WriteAsync("Hello World \n");
    await next(context);
});

app.Run(async (context) =>
{
    await context.Response.WriteAsync("Hello World 2");
});
```

- Ultimately, we need multiple middlewares for an application to behave appropriately.
- Middlewares has access to all the request and responses.
- Middleware defined using app.Run() will never call subsequent middleware.
- Middleware defined using app.Use() allows that middleware to pass control to the next item in the pipeline.
- Find when to use what - app.Run() or app.Use()

# Routing

- The Routing in ASP.NET Core MVC application is a mechanism in which it will inspect the incoming requests (i.e. URLs) and then mapped that request to the controllers and their action methods.
- Routing = URL + HTTP Methods (GET, POST, PUT, DELETE)
- This mapping is done by the routing rules which are defined by the application.
- We can do this by adding the Routing Middleware to the request processing pipeline.
- So, the ASP.NET Core Framework maps or connects the incoming Requests i.e. URLs to the Controllers action methods based on the routes configured in your application.
- Types of Routing supported by ASP.NET Core MVC. There are two ways:
  - Convention Based Routing
  - Attribute Based Routing (Preferred with Web API)

# Convention Based Routing

- Learn to implement convention based routing in ASP.NET Core MVC Web App and ASP.NET Core Empty Web App
- Learn to implement MVC in ASP.NET Core Empty Web App
- Add below code in Program.cs file to enable ASP.NET Core Empty Web App to use convention based routing with MVC:

```console
builder.Services.AddControllersWithViews();

app.MapDefaultControllerRoute();

app.MapControllerRoute(
    name: "default",
    pattern: "{controller=Home}/{action=Index}/{id?}");
```

- In Conventional Based Routing, the route is determined based on the conventions defined in the route templates which will map the incoming Requests (i.e. URLs) to controllers and their action methods.
- In ASP.NET Core MVC application, the Convention based Routes are defined within the Program.cs class file.
- In ASP.NET Core MVC application, it is the controller action method that is going to handle the incoming Requests i.e. URLs.
- For example, if we issue a request to the "/Home/Index" URL, then it is the Index action method of Home Controller class which is going to handle the request.
- Similarly, if you issue a request to the "/Home/Details/2" URL, then it is the Details action method of the Home Controller class which is going to process that request.
- Here the parameter value 2 is automatically mapped to the id parameter of the Details action method.

# Attribute Based Routing

- In Attribute-Based Routing, [Route] attribute is used to define the routes.
- Use a middleware **app.MapControllers()** to use Attribute based routing in your ASP.NET Core Web App. Mention the middleware in Program.cs file
- Tokens in Attribute Based Routing

```console
[Route("[controller]/[action]")]

[Route("")]
[Route("~/")]
[Route("~/Home")]
```

- In Attribute-Based Routing, the route is determined based on the attributes which are configured either at the controller level or at the action method level.
- We can use both Conventional and Attribute based routing in a single application.
- Changing the controller or action name does not require the route template to be changed.
- Token for controller is [controller]
- Token for action method is [action]
- We can use both tokens together [controller]/[action]

# Map, MapGet, MapPost, MapPut, MapDelete

- The MapGet method is used to define an endpoint.
- An endpoint is something that can be: Selected, by matching the URL and HTTP method.
- Executed, by running the delegate.

# Controllers

- URL Request => Routing => Controller => Action Method (Model, View)
- Controller manages the flow of the application.
- A Controller is used to define and group a set of actions.
- It is responsible for intercepting incoming requests and executing the appropriate application code.
- Controller is a backbone of MVC.
- Communicates with the models of the application and selects the required view to be rendered for the request.
- Allows separating the business logic of the application from the presentation logic.
- Incoming requests are mapped to actions through routing.
- Controllers help in managing complete flow of application including accepting input and rendering appropriate output.
- Controllers are basically C# classes that inherit from
  - Microsoft.AspNetCore.Mvc.Controller
- Controller along with its action method accepts incoming browser requests, retrieves required
  model information, and provides suitable responses.
- It is recommended that class name of a controller ends with suffix 'Controller'.
- Controllers are located in the root-level "Controllers" folder.
- In an ASP.NET CORE MVC application, a controller is responsible to:
  - Locate the appropriate method to call for an incoming request.
  - Validate the data of the incoming request before invoking the requested method.
  - Retrieve the request data and passing it to requested method as arguments.
  - Handle any exceptions that the requested method throws.
  - Help in rendering the view based on the result of the requested method.

# Action Methods

- A controller class can contain one or more action methods, also known as controller actions.
- Actions are the methods in controller class which are responsible for returning the view or Json data.
- Action methods are public methods in Controller classes.
- Find
  - return type : IActionResult
  - return type : ActionResult
  - return type : ViewResult
  - Difference between IActionResult and ActionResult
- Classes ViewResult, PartialViewResult, JsonResult, etc. have implemented interface IActionResult
- If the return type of an action method is set to IActionResult that means it can return variety of stuff. For example: view, partial-view, json, empty result etc.
- Action methods are responsible for processing the requests that are sent to the controller.
- Action methods can return multiple types of data.
- By default, it generates a response in the form of IActionResult Interface or ActionResult Abstract Class.
- Rules that you need to consider while creating an action method are as follows:
  - They must be declared as public
  - It cannot be private or protected
  - They can't be declared as static
- All the public methods inside a controller which respond to the URL are knows as Action Methods
- We can create multiple action methods in a controller
- You can invoke an action method by specifying a URL in the Web Browser containing the name of the controller and the action method to invoke.
- IActionResult
  - The IActionResult return type is appropriate when multiple ActionResult return types are possible in an action
  - IActionResult and ActionResult work as a container for other action results.
  - IActionResult is an interface and ActionResult is an abstract class
- Action Methods Returns
  - IActionResult
  - ActionResult
  - ContentResult
  - EmptyResult
  - JsonResult
  - PartialViewResult
  - ViewResult
  - ViewComponentResult

# View - Razor Syntax & Razor View Engine

- Can use the following in the Razor View:
  - Inline expression statement
  - Declaring variable using var keyword
  - Multi statement code block
  - Conditional statement if-else, switch, etc.
  - Can use arrays, loops, etc.
- View
  - A view provides the User Interface of the application to the user.
  - A view is used to display content of an application and also to accept user inputs.
  - View uses model data to create the UI
  - View contains both HTML markup and C# code that runs on the web server
  - View has a file extension .cshtml
- Razor
  - Razor is a syntax, based on the ASP.NET Core Framework that allows creating views.
  - Razor is used to simplify the process of creating views.
  - Razor is simple and easy to understand for users who are familiar with the C#.NET programming language.
  - While creating a Razor View, you should consider following rules:
    - Start inline expressions with @
    - Enclose code blocks between @ {...}
    - Variables are declared with the var keyword
    - Enclose strings in quotation marks
    - End a Razor code statement with semicolon in case of multiple lines
    - Use the .cshtml extension to store a Razor View file that uses C#.NET as the programming language
- Razor Engine
  - The MVC Framework uses a view engine to convert the code of a view into HTML markup that a browser can understand.
  - Razor engine is used as the default view engine by the MVC Framework
  - Compiles a view of your application when the view is requested for the first time.
  - Delivers the compiled view for subsequent requests until you make changes to the view
  - Doesn't introduce a new set of programming language, but provides template markup syntax to segregate HTML markup and programming code in a view.
  - First requires identifying the server-side code from the markup code to interpret the server side code embedded inside a view file.
  - Uses the @ symbol, to separate the server-side code from the markup code

# Layout View \_Layout.cshtml (Master Page)

- Layout view provides consistent look for all the views in a web application.
- Layout View is as same as ASP.NET Web Forms Master Page
- Extension of Layout View is .cshtml
- Default name of Layout View is \_Layout.cshtml
- Layout View files are usually located in Views/Shared
- An application can have multiple Layout Views
- Layout property is used to connect Layout View with a view.
  - Layout = "~/Views/Shared/\_Layout.cshtml"

# View Start File \_ViewStart.cshtml

- Why do we need \_ViewStart.cshtml
  - Suppose, we have 100 views in our application and all the 100 views want to use the same layout file
  - Then we need to set the Layout property in all the 100 views.
  - This violates the DRY Principle and has the following disadvantages.
    - Redundant Code
    - Maintenance Overhead
  - Commonly \_ViewStart.cshtml file is located in Views folder
- Tasks
  - If we have Multiple Layout Views then how we can use multiple layout views with View Start file.
  - IF we specify Layout Property in a View and as well as in \_ViewStart then it gives priority to the Layout Property
  - If we don't want a Layout View in a particular view then set Layout Property null (Layout = null)
  - We can select a layout conditionally in ViewStart file.

# Passing Data From Controller to View

- In an ASP.NET CORE MVC application, a controller typically performs the business logic of the application and needs to return the result to the user through a view.
- You can use the following objects to pass data between controller and view:
  - ViewData
  - ViewBag
  - TempData
  - Strongly Typed Views
- **ViewData**
  - It passes data from a controller to a view
  - The general syntax of ViewData is as follows:
    - `ViewData["<Key>"] = <Value>;`
    - Key: is a string value to identify the object present in ViewData
    - Value: is the object present in ViewData. This object may be a string, object, list, array or a different type such as int, char, float, double, DateTime etc.
  - It is a dictionary of objects that is derived from the ViewDataDictionary class.
  - Some of the characteristics of ViewData are as follows:
    - The life of a ViewData object exists only during the current request
    - You can't access ViewData of one action method into another
    - The value of ViewData becomes null if the request is redirected
    - ViewData requires typecasting when you use complex data type to avoid errors
    - Note: ViewData doesn't provide compile time error checking. For example- if you misspell keys you wouldn't get any compile time errors. You get to know about the error only at runtime.
- **ViewBag**
  - It passes data from a controller to a view
  - The general syntax of ViewData is as follows:
    - `ViewBag.<PropertyName> = <Value>;`
    - Property: is a String value that represents a property of ViewBag.
    - Value: is the value of the property of ViewBag. It may be a string, object, list, array or a different type such as int, char, float, double, DateTime etc.
  - ViewBag is a dynamic data type property of the base class of all the controllers, which is the ControllerBase class.
  - ViewBag is a dynamic data type, which internally uses ViewData to store values.
  - ViewBag and ViewData can access each other interchangeably.
  - ViewBag exists only for the current request and becomes null if the request is redirected.
  - ViewBag is a dynamic data property based on the dynamic features introduces in C# 4.0
  - ViewBag doesn't required typecasting when you use complex data type.
  - Note: ViewBag does not provide compile time error checking. For Example- if you mis-spell property you wouldn't get any compile time errors. You get to know about the error only at runtime.
- **TempData**
  - It passes data from a controller to a view
  - TempData is used only for current or subsequent requests as it is a very short-lived instance. It is accessible once only.
  - Redirecting is the only case when users can rely on TempData.
  - When redirecting, current request is killed, and a new request is created on the server to serve the redirected view.
  - Sharing data between the controller actions are done through the ASP.NET MVC TempData dictionary.
  - TempData is a Dictionary object derived from the TempDataDictionary class.
  - TempData stores data as key-value pairs.
  - TempData value must be type cast before use, if it stores any complex data type value.
  - Check for null values to avoid runtime error.
  - TempData allows passing data from the current request to th subsequent request during request redirection.
  - `TempData[<Key>] = <Value>`;
  - Key: is a string value to identity the object present in TempData
  - Value: is the object present in TempData
  - TempData in ASP.NET Core MVC can be used to store temporary data which can be used in the subsequent request.
  - TempData will be cleared out after the completion of a subsequent request.
  - Call TempData.Keep() to keep all the values of TempData in a third request.

# Models

- A model is a class with .cs (for C#) as an extension having both properties and methods.
- Models are used to set or get the data.
- Student Model
  - rollNo
  - Name
  - Gender
  - Class
- If your application doesn't have data, then there is no need for a model.
- If your application has data, then you need model.
- The Models in ASP.NET Core MVC contains a set of classes that are used to represent the domain data (you can also say the business data) as well as it also contains logic to manage the domain/business data.
- So, in simple words, we can say that the models in ASP.NET Core MVC Application are used to manage the data.
- If you are working with any Web Application that is based on MVC Design Pattern, then in that MVC Application, three things are common i.e. Model, View, and Controller.
- The Controllers are used to manage the overall flow of the application. Models are responsible for the data and these data are used on Views Views are basically the HTML pages that get rendered into the browser of the client.
- We can perform operations like insert, update delete by using Models.
- Note: It is not mandatory, but it is a good programming practice to store all the model classes within the Models folder.

# Repository Pattern

- With the Repository pattern, we create an abstraction layer between the data access and the business logic layer of an application.
- By using it, we are promoting a more loosely coupled approach to access our data from the database.
- Also, the code is cleaner and easier to maintain and reuse.
- Repository is a combination of two things (interface and class) Ex. for student table we have IStudent interface and StudentRepository class in a separate folder Repository

# How to Pass Model Data from Controller to View Using ViewData, ViewBag & TempData

# Strongly Typed Views

- Strongly typed view or strongly typed object is used to pass data from controller to a view.
- The view which binds with any model is called as strongly typed view.
- You can bind any class as a model to view.
- You can access model properties on that view.
- You can use data associated with model to render controls.
- The view that is designed by targeting specific model class object then that view is called 'Strongly Typed View'.
- In strongly typed view, view is bind with corresponding model class object or list of objects.

# Install Bootstrap, Tailwind, jQuery

- All Static Files like bootstrap, css, js, jquery are placed inside wwwroot folder.
- Images folder is also placed in wwwroot folder
- app.UseStaticFiIes(); without this method you cannot access static files like bootstrap, css, js, jquery etc.
- Libman.json (Library Manager) file contains all the configurations for client side libraries.

# \_ViewImports.cshtml
