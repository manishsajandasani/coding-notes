# What I Learnt (Topics)

- Installation of @angular/cli
- Check version of @angular/cli
- Create a new Angular Project and Run it
- Folder Structure of an Angular App
- Create Angular Component (Manually)
- Create Angular Component (Angular CLI)
- Component Decorator (selector, template, templateUrl, styles, styleUrls)
- constructor method
- OnInit Interface and ngOnInit Method
- AfterViewInit Interface and ngAfterViewInit Method
- ChangeDetectorRef, constructor(private cdRef: ChangeDetectorRef), this.cdRef.detectChanges();
- Create Variables of every DataType, Arrays of every DataType, Array of Objects, etc.
- Data Binding / String Interpolation
- Sharing Data between Components
  - Parent to Child - `@Input` Decorator
  - Child to Parent - `@ViewChild` Decorator
  - Child to Parent - `@Output` Decorator and `Event Emitter`
- Data Binding `Brackets []`
- Event Binding `Parenthesis ()`
- One Way Data Binding
  - String Interpolation - `{{ title }}`
  - Property Binding - `[href] = '...'`
  - Class Binding - `[class.text-red] = '...'`
  - Style Binding - `[style.color] = '...'`
- Two Way Data Binding
  - Import FormsModule and use `[(ngModel)] = '...'`
- Event Binding
- Event Filtering
- Template Variable
- Directives
  - Component Directive
  - Structural Directive
    - ngFor (Use of Array Index + Change Detection)
    - ngIf with then and else condition
    - ngTemplate with Template Variables and `ng-template` tag
    - ngSwitchCase, ngSwitchDefault, ngSwitch Property Binding
  - Attribute Directive
    - ngClass
    - ngStyle
  - Custom Directive (Didn't Learn)
- Pipes
  - Uppercase
  - Lowercase
  - Number/Decimal
  - Currency
  - Date
  - JSON
  - Percent
  - Slice
  - Pass Params to Pipes
  - Create Custom Pipes from scratch
  - Create Custom Pipes using Angular CLI
  - Create Custom Pipes using Angular CLI with Arguments
- Services
  - Create Service from Scratch
  - Create Service using Angular CLI
  - Service Registration
    - Component Level
    - Module Level
    - Root Level (@Injectable Decorator)
  - Use Data Members of a Service (By Creating Instance)
  - Use Data Members of a Service (By Dependency Injection)
  - Perform CRUD Operations in Services
  - Create Interface to act as a Blueprint for the Object in order to avoid data member errors on the compile time (Data Modeling)

# What is Angular?

- It's a frontend JS framework to build client side applications using HTML, CSS, and JavaScript.

# What is SPA?

- Stands for Single Page Application.
- A SPA is an app that doesn't need to reload the page during its use and it works withing a web browser.

# What is Angular CLI?

- It's a Command Line Interface tool that is used to **Create, Compile, Update, Develop, Scaffold, and Maintain** an Angular Application directly from the Command Shell.

# How to setup Angular CLI?

- cmd: `npm install -g @angular/cli`
- cmd: `ng version || ng v`

# Generate an Angular App using Angular CLI?

- cmd: `ng new <project-name>`
- cmd: `ng serve`
- cmd: `ng serve -port 4300`

# About Angular Project's File Structure A-Z

- tslint.json
- tsconfig.spec.json
- tsconfig.app.json
- tsconfig.json
- README.md
- package.json
- node_modules folder
- package-lock.json
- karma.conf.js
- angular.json
- .gitignore
- .editorconfig
- .browserslistrc
- e2e folder
- src folder
  - app
    - app-routing.module.ts
    - app.component.css
    - app.component.html
    - app.component.spec.ts
    - app.component.ts
    - app.module.ts
  - assets
    - .gitkeep
  - environments
    - environment.prod.ts
    - environment.ts
  - favicon.ico
  - index.html
  - main.ts
  - polyfills.ts
  - styles.css
  - test.ts

# What is Angular Component & How to use it?

- Angular framework is a component based frontend framework
- Components are the main building block of an Angular app
- Without components we cannot build a proper angular app
- A component is a combination of data html template and logics
- A component represent an area of a view that shows inside the browser
- A component gets loaded inside the browser

# Create Angular Components

- Create Angular Component From Scratch (Manually)
- Generate Components using Angular CLI

```js
cmd: ng g c post
CREATE src/app/post/post.component.html (19 bytes)
CREATE src/app/post/post.component.spec.ts (545 bytes)
CREATE src/app/post/post.component.ts (194 bytes)
CREATE src/app/post/post.component.css (0 bytes)
UPDATE src/app/app.module.ts (549 bytes)
```

- How to Add HTML Markups and Styles to a component [Component Decorator, template, templateUrl, styles, styleUrls]
- Implementation of OnInit Interface and ngOnInit (method and Life Cycle Hook)

```js
import { Component, OnInit } from "@angular/core";

@Component({
  selector: "app-post",
  templateUrl: "./post.component.html",
  styleUrls: ["./post.component.css"],
})
export class PostComponent implements OnInit {
  constructor() {}
  ngOnInit(): void {
    console.log("Loaded");
  }
}
```

# Angular Data Binding

- In order to use the variables of `.ts file` into the `.html file` of a component, you have to create the scope. In Angular you can create the scope with this `{{  }}`. Ex. `{{ title }}`. This is what we call `Data Binding` or `String Interpolation` in Angular.
- Inside these curly braces we can put any valid JavaScript code. Some examples are:

  - `{{ 100 + 50 }}`
  - `{{ 2*5 }}`
  - `{{ null == undefined }}`
  - `{{ null === undefined }}`
  - `{{ undefined }}`
  - `{{ 3 / 0 }}`

# How to Communicate or (Sharing Data) Between Two Components

- Parent to child Component via `@input Decorator`. `@Input Decorator` is used to share data between Parent Component and a Child Component.
- Child to Parent Component Via `@ViewChild Decorator`
- Child to Parent when there is Event, using the `@Output Decorator` and `Event Emitter`. This approach is ideal when we want to share data changes that occur on things like button clicks, form entries, and other user events.

# Data Display and Event Handling

- For `Data Binding` we use `Brackets []`
- For `Event Binding` we use `Parenthesis ()`
- **One Way Data Binding:** Component to HTML (Can only bind data component to html). It is Uni Directional
  - String Interpolation (used to show dynamic data inside the HTML page) => `{{title}}`
  - Property Binding => `[src]`
  - CSS Class Binding => `[class.text-red]`
  - CSS Style Binding => `[style.color]`
- **Two Way Data Binding:** Component to HTML and Vice Versa (Can bind data component to html and vice versa). It is Bi-Directional
  - Two Way Binding => `[(ngModel)]`
- Handle Events like click, keyup, filtering etc.
  - Event Binding
  - Event Filtering
- Template Variable

# Angular Directives

- What is Angular Directive and How to use
  - An angular directive is special type of technology that can manipulate the DOM object
  - Directives can add html elements remove html elements from the DOM dynamically.
  - Directives are Components Without a View. Whatever you can do with a Directive, you can do with a Component.
  - Angular Components are Directives With a View. Whatever you can do with a Component, you can't do with a Directive.
- Types of Angular Directive
  - Component Directive => which is an angular directive with a template view
  - Structural Directive => which can change the DOM layout by adding and removing DOM elements.
  - Attribute Directive => which can change the appearance or behavior of an element, component, or another directive.
  - Custom Directive => which can create our custom directive from scratch.
- Structural Directive
  - Responsible for the HTML Layout
  - Manipulate the DOM Structure by adding and removing HTML Elements.
  - Can be Identified With Leading `*` Symbol
  - Types
    - ngFor Directive (Usage of Array Index)
      - We use NgFor Directive to Render an Array inside the View
      - NgFor Directive is a Structural Directive.
      - With NgFor Directive we can Manipulate The DOM.
      - Loop through an array, array of objects,
    - ngIf Directive
    - ngTemplate Directive
      - It works with structural directives only. `<ng-template>...</ng-template>` is a tag which is used to show stuff conditionally. We can't use it as a normal HTML Tag.
      - It also works with truthy and falsy values.
    - ngSwitchCase Directive
- Attribute Directive (Used with [])
  - Change the appearance or the behaviour of a DOM Element
  - Types
    - ngStyle
    - ngClass
- Learn Difference of Structural and Attribute Directive
- Change Detection (Adding or Removing Items in Real Time)

# Angular Pipes

- What is Angular Pipe and How to use.
  - Pipes are used to transform data into a particular format when we only need that data transformed 'in' a template or the HTML View.
  - Examples of Pipes
    - Angular Number/Decimal Pipe
    - Angular Currency Pipe
- What are the inbuilt Pipes in Angular.
  - Uppercase Pipe
  - Lowercase Pipe
  - Decimal / Number Pipe
  - Currency Pipe
  - Date Pipe
  - JSON Pipe
  - Percent Pipe
  - Slice Pipe
- How to pass parameters to an Angular Pipe.
- How to create a custom Pipe from Scratch.
- How to create a custom Pipe using Angular CLI.
  - `ng g pipe Pipes/AppendCLI`

# Angular Services

- What is Angular Service & How to use?
  - We use Angular Services to share data and common methods among components whether there is relation between components or not.
- How to Create Angular Service From Scratch?
- Service Registration (https://www.educative.io/answers/how-to-use-the-injectable-decorator-in-angular)
  - Root Level
  - Module Level
  - Component Level
- What is Dependency Injection (DI Providers and Injectable Decorators) & How to use?
  - We shouldn't be using this in every component decorator `providers: [PostService]`. This would create hundreds of instances of a Service.
  - Instead, mention the ServiceProvider in `app.module.ts` like this `providers: [PostService]`. This would create only one instance and will be accessible throughout the application's components. Or
  - We can use Injectable Decorator in the ServiceProvider class like this `@Injectable({providedIn : "root"})` also import this `import { Injectable } from "@angular/core";`
- Generate Angular Services using Angular CLI?
  - `ng g s Services/user`
- CRUD with Angular Service
- What is Data Modeling and Angular Interface?
  `ng g i Models/usermodel`

# Angular Forms

- What are the forms types in Angular?
  - Template Driven Form
  - Reactive Form
- What is Template Driven Form and how to use that?
  - ngForm Directive on the form tag to create formGroup Class Instance
  - ngModel Directive on the input element to create fromControl Class Instance
- How to Validate forms user inputs (Form Validation) in Template Driven Approach?
- How to control Enable / Disable state of a button?
