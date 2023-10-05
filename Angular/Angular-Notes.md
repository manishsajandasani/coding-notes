# Angular Related Questions and Doubts

- package.json Vs. package-lock.json file
- How to install specific version of Angular?
- How to install 2 different versions of Angular?
- How to upgrade to newer version of Angular?
- Find use of each and every file and folder of the Angular Application
- Which files and folders to be ignored while uploading Angular App. to GitHub
- How to change environments : development Vs. production?
- What is polyfill file?
- Difference between [ngIf] and *ngIf?
- What are Structural Directives?
- Learn Directives - Built-In, Attribute, Structural, Directive Composition API

# Angular Files and Folders

- package.json
- node_modules
- src folder
    - app
    - assets
    - environments
    - index.html
    - main.js
    - style.css
- package-lock.json
- angular.json
- tsconfig files
- .browserslistrc
- karma.conf.js
- polyfills.ts

# Angular Topics To Learn About

- Interpolation
- Component
- Module
- Decorators 
- Class
- Interface

# Angular Commands

```console
node -v
npm -v
npm install -g @angular/cli
npm uninstall -g @angular/cli
npm install -g @angular/cli@10.0.0
ng version
ng new blog
ng serve
npm cache clean --force
```

# Angular CLI Commands

```html
ng version
ng help
ng serve
ng build
ng deploy
ng generate
ng generate component login
ng g component register
ng g module user-auth
ng g m user-auth
ng g c user-auth/sign-out

npm config set legacy-peer-deps true  (to resolve installing bootstrap error)
ng add @ng-bootstrap/ng-bootstrap

ng add @angular/material
```

# Generate a component via CLI

```console
ng generate component login
CREATE src/app/login/login.component.html (20 bytes)
CREATE src/app/login/login.component.spec.ts (552 bytes)
CREATE src/app/login/login.component.ts (198 bytes)
CREATE src/app/login/login.component.css (0 bytes)
UPDATE src/app/app.module.ts (392 bytes)

In src/app/
login folder gets created with four files:
- login.component.css
- login.component.html
- login.component.spec.ts
- login.component.ts

==> app.module.ts file
import { LoginComponent } from './login/login.component';     <==== (this line gets added)

@NgModule({
  declarations: [
    AppComponent,
    LoginComponent    <==== (this line gets added)
  ],
  .......
  .......
  .......
})
```

# Generate a module via CLI

```console
ng g module user-auth
CREATE src/app/user-auth/user-auth.module.ts (194 bytes)

In src/app/
user-auth folder gets created with one file:
- user-auth.module.ts
```

# Generate a component inside a module via CLI

```console
ng g c user-auth/sign-out
CREATE src/app/user-auth/sign-out/sign-out.component.html (23 bytes)
CREATE src/app/user-auth/sign-out/sign-out.component.spec.ts (567 bytes)
CREATE src/app/user-auth/sign-out/sign-out.component.ts (209 bytes)
CREATE src/app/user-auth/sign-out/sign-out.component.css (0 bytes)
UPDATE src/app/user-auth/user-auth.module.ts (368 bytes)

==> user-auth.module.ts file
import { SignInComponent } from './sign-in/sign-in.component';  (added)
import { SignOutComponent } from './sign-out/sign-out.component';  (added)

@NgModule({
  declarations: [
    SignInComponent,  (added)
    SignOutComponent  (added)
  ],
  imports: [
    CommonModule
  ]
})
```

# Generate a class via CLI

```console
ng g class Dummy
CREATE src/app/dummy.spec.ts (150 bytes)
CREATE src/app/dummy.ts (23 bytes)
```

# Generate an interface via CLI

```console
ng g interface dummyInterface
CREATE src/app/dummy-interface.ts (36 bytes)
```

# Interpolation

- Used to display dynamic data (properties, functions) on the HTML page. {{ ... }}
- Dynamic data is defined in the .component.ts file
- We can print properties, functions, objects, arrays, arithmetic calculations, etc. 
- We can use it as a class name. 
- We can't do following:
    - It can't assign value to a variable. 
    - We can't check typeof of a variable.
    - We can't increment or decrement values.
    - We can't use new operator.
    ```html
    <h2>{{ employee.name = "Sanjay" }}</h2>
    <h2>{{ typeof title }}</h2>
    <h2>{{ count++ }}</h2>
    ```
```js
==> app.component.ts file
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  title = 'Angular Applicaton Blog';
  employee = {
    name: "Manish",
    age: 31,
    occupation: "Full Stack Developer"
  }
  getEmployeeName = () => {
    return this.employee.name;
  }
  count = 10
}

==> app.component.html
<h1>Namaste World!!!</h1>
<h2>This is {{ title }}</h2>
<h2>Occupation is {{ employee.occupation }}</h2>
<h2>Employee name is {{ getEmployeeName() }}</h2>
<h2>{{ 2*10 }}</h2>
<h2>{{ title=="blog" }}</h2>
<h2 class="{{ employee.name }}">{{ employee.name == "Manish" }}</h2>

<!-- <h2>{{ employee.name = "Sanjay" }}</h2> -->
<!-- <h2>{{ typeof title }}</h2> -->
<!-- <h2>{{ count++ }}</h2> -->
```

# Component

- What is Component?
- How to generate a component?
- How to use/display a component?
  - Use the selector name as an element mentioned in the .component.ts file in another .component.html file. This will print the component's HTML content. 
  ```html
  <app-login></app-login>
  ```
  - We can change the name of the component. Change selector name property in the .component.ts file.  
- Interview Questions

# Component with Inline Style and Template

- When we don't want to pass the urls of template and style, we can use this feature.
- Interview Questions
  - How to create inline template, style, or both at the same time.
  - Why to create inline template and style.

```console
ng g c user-inline-style --inline-style
CREATE src/app/user-inline-style/user-inline-style.component.html (32 bytes)
CREATE src/app/user-inline-style/user-inline-style.component.spec.ts (624 bytes)
CREATE src/app/user-inline-style/user-inline-style.component.ts (209 bytes)
UPDATE src/app/app.module.ts (514 bytes)

==> user-inline-style.component.ts
import { Component } from '@angular/core';

@Component({
  selector: 'app-user-inline-style',
  templateUrl: './user-inline-style.component.html',
  styles: [
    `.custom {
      color: red;
    }`
  ]
})
export class UserInlineStyleComponent {

}

==> user-inline-style.component.html
<h1 class="custom">user-inline-style works!</h1>
```

```console
ng g c user-inline-template --inline-template
CREATE src/app/user-inline-template/user-inline-template.component.spec.ts (645 bytes)
CREATE src/app/user-inline-template/user-inline-template.component.ts (270 bytes)
CREATE src/app/user-inline-template/user-inline-template.component.css (0 bytes)
UPDATE src/app/app.module.ts (648 bytes)

==> user-inline-template.component.ts
import { Component } from '@angular/core';

@Component({
  selector: 'app-user-inline-template',
  template: `
    <h1 class="template-style">
      user-inline-template works!
    </h1>
  `,
  styleUrls: ['./user-inline-template.component.css']
})
export class UserInlineTemplateComponent {

}

==> user-inline-template.component.css
.template-style {
    background: green;
    color: #fff;
    padding: 15px;
}
```

```console
ng g c inline-template-style-both --inline-template --inline-style
CREATE src/app/inline-template-style-both/inline-template-style-both.component.spec.ts (681 bytes)
CREATE src/app/inline-template-style-both/inline-template-style-both.component.ts (249 bytes)
UPDATE src/app/app.module.ts (804 bytes)

==> inline-template-style-both.component.ts
import { Component } from '@angular/core';

@Component({
  selector: 'app-inline-template-style-both',
  template: `
    <h1 id="both-inline">
      inline-template-style-both works!
    </h1>
  `,
  styles: [
    `#both-inline {
      color: orange;
    }`
  ]
})
export class InlineTemplateStyleBothComponent {

}

==> app.component.html
<app-user-inline-style></app-user-inline-style>
<app-user-inline-template></app-user-inline-template>
<app-inline-template-style-both></app-inline-template-style-both>
```

# Module

- What is Module?
- How to make and use Module?
- Make component inside Module.
- What is app.module.ts file?
- Why to use Module?

```console
ng g c user-auth/sign-out
CREATE src/app/user-auth/sign-out/sign-out.component.html (23 bytes)
CREATE src/app/user-auth/sign-out/sign-out.component.spec.ts (567 bytes)
CREATE src/app/user-auth/sign-out/sign-out.component.ts (209 bytes)
CREATE src/app/user-auth/sign-out/sign-out.component.css (0 bytes)
UPDATE src/app/user-auth/user-auth.module.ts (368 bytes)

==> user-auth.module.ts file
import { NgModule } from '@angular/core';
import { CommonModule } from '@angular/common';
import { SignInComponent } from './sign-in/sign-in.component';
import { SignOutComponent } from './sign-out/sign-out.component';

@NgModule({
  declarations: [
    SignInComponent,
    SignOutComponent
  ],
  imports: [
    CommonModule
  ],
  exports: [
    SignInComponent,
    SignOutComponent
  ]
})
export class UserAuthModule { }

==> app.module.ts
import { UserAuthModule } from './user-auth/user-auth.module';

imports: [
  BrowserModule,
  UserAuthModule  (added)
],

==> app.component.html
<app-sign-in></app-sign-in>
<app-sign-out></app-sign-out>
```

# Make and Call Function

- Define Function
  - We have to define the function in the .component.ts file. We can call it in the .component.html file on any JavaScript event.
  - Remember from Angular 16, it's mandatory to mention the type of the function parameters
- Call a Function on a Button Click
- Params in Function 
- Interview Questions
  - Why do we need to provide datatype of the param in the function? 
    - Ans. It's because the strict mode is now set to true in the tsconfig.json file ("strict": true)

```console
==> app.component.ts 
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  printName() {
    console.log(`My name is Manish`);
  }

  printName2(theName: string) {
    console.log(`My name is ${theName}`);
  }
}

==> app.component.html 
<button (click)="printName()">Print Name</button> <br> <br>
<button (click)="printName2('Purab')">Print Name 2</button>
```

# Important Events

- Call Same Function with Different Events
- Events with Input Box and Get Value

```console
ng g c function-different-events
CREATE src/app/function-different-events/function-different-events.component.html (40 bytes)
CREATE src/app/function-different-events/function-different-events.component.spec.ts (680 bytes)
CREATE src/app/function-different-events/function-different-events.component.ts (276 bytes)
CREATE src/app/function-different-events/function-different-events.component.css (0 bytes)
UPDATE src/app/app.module.ts (1041 bytes)

==> app.component.html
<app-function-different-events></app-function-different-events>

==> function-different-events.component.html
<input #btn1 (keyup)="callFunc(btn1.value)" placeholder="Event Keyup"> <br> <br>
<input #btn2 (keydown)="callFunc(btn2.value)" placeholder="Event Keydown"> <br> <br>
<input #btn3 (blur)="callFunc(btn3.value)" placeholder="Event Blur"> <br> <br>
<input #btn4 (input)="callFunc(btn4.value)" placeholder="Event Input"> <br> <br>
<h1 #btn5 (mouseover)="callFunc(btn5.innerText)">Hover mouse over me</h1>
<h1 #btn6 (mouseleave)="callFunc(btn6.innerText)">Hover Left</h1>

==> function-different-events.component.ts
import { Component } from '@angular/core';

@Component({
  selector: 'app-function-different-events',
  templateUrl: './function-different-events.component.html',
  styleUrls: ['./function-different-events.component.css']
})
export class FunctionDifferentEventsComponent {
  callFunc(data: string) {
    console.log(data);
  }
}
```

# Get TextBox Value and Print

```console
==> function-different-events.component.html
<input #box (keyup)="printValue(box.value, box.placeholder, box.name)" placeholder="Input Box" name="username">
<h1>{{ boxValue }} == {{ placeholderValue }} == {{ nameValue }}</h1>

==> function-different-events.component.ts
import { Component } from '@angular/core';

@Component({
  selector: 'app-function-different-events',
  templateUrl: './function-different-events.component.html',
  styleUrls: ['./function-different-events.component.css']
})
export class FunctionDifferentEventsComponent {
  boxValue: string = "";
  placeholderValue: string = "";
  nameValue: string = "";

  printValue(b: string, ph: string, na: string) {
    this.boxValue = b;
    this.placeholderValue = ph;
    this.nameValue = na;
  }
}
```

# Counter Example

```console
==> function-different-events.component.html
<button (click)="counter('minus')">Down</button>
<p>Count = {{ count }}</p>
<button (click)="counter('plus')">Up</button>

==> function-different-events.component.ts
import { Component } from '@angular/core';

@Component({
  selector: 'app-function-different-events',
  templateUrl: './function-different-events.component.html',
  styleUrls: ['./function-different-events.component.css']
})
export class FunctionDifferentEventsComponent {
  count: number = 0;
  counter(type: string) {
    type === "plus" ? this.count++ : this.count--;
  }
}
```

# Global + Component + Internal + Inline Style CSS

- Inline => Internal => Global => Component (Priority / Specificity)

```console
==> styles.css
.global-css-padding {
    padding: 25px;
}

.heading {
    text-align: left;
}

==> app.component.css
.component-css-clr-blue {
    color: blue;
}

.heading {
    text-align: center;
}

==> app.component.html
<style>
    .internal-css-border {
        border: 3px solid green;
    }

    .heading {
        text-align: right;
    }
</style>

<h1 class="component-css-clr-blue internal-css-border global-css-padding heading" style="text-align: justify;">
    Lorem ipsum dolor, sit amet consectetur adipisicing elit. Sint, consectetur totam sapiente fugit tempora atque culpa
    possimus quibusdam! Libero sapiente facere temporibus, natus culpa ipsam dolorem quisquam id similique veritatis
</h1>
```

# Property Binding

- What is Property Binding?
- Diff. between Property Binding and Interpolation?
  - Interpolation works with number and string only.
  - Property Binding works with boolean values also.
  - If we need to change any attribute's value - use Property Binding.

```console
==> app.component.ts
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  inputValue: string = "Manish";
  disable: boolean = false;
}

==> app.component.html
<!-- Interpolation -->
<!-- Although disable property is false but due to interpolation it's working like string not boolean -->
<div>
    <input type="text" name="username" value="{{ inputValue }}" disabled="{{ disable }}">
</div>

<!-- Property Binding -->
<div style="margin-top: 15px;">
    <input type="text" name="username" [value]="inputValue" [disabled]=disable>
</div>
```

# If-Else with Toggle Element Example

```console
==> app.component.ts
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  show: boolean = true;
  show2: boolean = false;
  show3: boolean = false;
  married: string = "No";

  showOrHide() {
    this.show = !this.show;
  }
}

==> app.component.html
<!-- If-Else Condition -->
<!-- 1st Example -->
<h1 *ngIf="show">
    Show My Code
</h1>
<button (click)="showOrHide()">Show / Hide</button>

<!-- 2nd Example -->
<h1 *ngIf="show2 else theElseBlock">
    This is IF Condition
</h1>
<ng-template #theElseBlock>
    <h1>
        This is Else Condition
    </h1>
</ng-template>

<!-- 3rd Example -->
<h1 *ngIf="show3; then ifyblock else elsyblock"></h1>
<ng-template #ifyblock>
    <h1>
        If Me
    </h1>
</ng-template>
<ng-template #elsyblock>
    <h1>
        Else Me
    </h1>
</ng-template>

<!-- 4th Example -->
<h1 *ngIf="married == 'Yes'; then nobachelor else bachelor"></h1>
<ng-template #nobachelor>
    <h1>
        Not a Bachelor Anymore
    </h1>
</ng-template>
<ng-template #bachelor>
    <h1>
        Always a Bachelor
    </h1>
</ng-template>
```

# Multiple If Condition

```console
==> app.component.ts
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  color: string = "green";
}

==> app.component.html
<!-- Multiple If Condition -->
<ng-template [ngIf]="color==='blue'">
    <h1 style="color:blue;">Blue Color</h1>
</ng-template>

<ng-template [ngIf]="color==='green'">
    <h1 style="color:green;">Green Color</h1>
</ng-template>

<ng-template [ngIf]="color==='red'">
    <h1 style="color:red;">Red Color</h1>
</ng-template>
```

# Switch Case

```console
==> app.component.ts
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  color: string = "xyz";
}

==> app.component.html
<!-- Switch Case -->
<div [ngSwitch]="color">
    <h1 *ngSwitchCase="'green'" style="color: green;">Green Color</h1>
    <h1 *ngSwitchCase="'red'" style="color: red;">Red Color</h1>
    <h1 *ngSwitchCase="'blue'" style="color: blue;">Blue Color</h1>
    <h1 *ngSwitchCase="'orange'" style="color: orange;">Orange Color</h1>
    <h1 *ngSwitchDefault style="color: black;">Invalid Color Type</h1>
</div>
```

# Loop through an array and objects' array

```console
==> app.component.ts
export class AppComponent {
  fruits: string[] = ["Banana", "Chiku", "Watermelon", "Cherry", "Pineapple"];
  userDetails: any[] = [
    { name: "Manish", age: 31, email: "sajan@gmail.com" },
    { name: "Sanjay", age: 32, email: "sanjay@gmail.com" },
    { name: "Kailash", age: 33, email: "kailash@gmail.com" },
    { name: "Murli", age: 34, email: "murli@gmail.com" }
  ]
}

==> app.component.html
<!-- Looping an Array -->
<ul>
    <li *ngFor="let fruit of fruits">{{ fruit }}</li>
</ul>

<!-- Looping an Object's Array -->
<table border="2" cellspacing="10" cellpadding="10">
    <tr *ngFor="let user of userDetails">
        <td>Name</td>
        <td>{{ user.name }}</td>
        <td>Age</td>
        <td>{{ user.age }}</td>
        <td>Email</td>
        <td>{{ user.email }}</td>
    </tr>
</table>
```

# Nested Loop

```console
==> app.component.ts
export class AppComponent {
  userDetails: any[] = [
    { name: "Monu", age: 31, email: "sajan@gmail.com", educations: ["10th", "12th"] },
    { name: "Shambhu", age: 32, email: "sanjay@gmail.com", educations: ["10th", "12th", "BCA"] },
    { name: "Pappu", age: 33, email: "kailash@gmail.com", educations: ["10th", "12th", "BBA", "PGDCA"] },
    { name: "Pushpa", age: 34, email: "murli@gmail.com", educations: ["8th"] }
  ]
}

==> app.component.html
<!-- Nested Loop -->
<table border="2" cellspacing="10" cellpadding="10" width="100%">
    <tr *ngFor="let user of userDetails">
        <td>Name</td>
        <td>{{ user.name }}</td>
        <td>Age</td>
        <td>{{ user.age }}</td>
        <td>Email</td>
        <td>{{ user.email }}</td>
        <td>Education</td>
        <td>
            <ul style="padding: 15px 15px 15px 25px;">
                <li *ngFor="let education of user.educations">{{ education }}</li>
            </ul>
        </td>
    </tr>
</table>
```

# Style Binding

```console
==> app.component.ts
export class AppComponent {
  color = "red";
  textAlign = "left";

  updateStyle() {
    this.color = "yellowgreen";
    this.textAlign = "center";
  }
}

==> app.component.html
<!-- Style Binding -->
<h1 [style.color]="color">Heading</h1>
<p [style.textAlign]="textAlign">
    Lorem ipsum dolor sit amet consectetur adipisicing elit. Eos pariatur, delectus, cupiditate minima dolorem
    voluptatem maxime modi corporis placeat enim recusandae accusantium esse alias, perferendis velit veritatis nobis
    nostrum tempore fugit? Vitae molestiae magnam labore nostrum reprehenderit, deleniti ullam repellendus nobis modi
    ipsum vero voluptates nulla dolores quod possimus nam?
</p>

<button (click)="updateStyle()">
    Update Style
</button>
```

# Basic Angular Form

```console
==> app.module.ts
import { FormsModule } from '@angular/forms';
imports: [
  BrowserModule,
  FormsModule (added)
]

==> app.component.ts
export class AppComponent {
  userData: any = {};
  showInfo: boolean = false;
  submitData(data: NgForm) {
    this.userData = data;
    this.showInfo = true;
  }
}

==> app.component.html
<!-- NgForm -->
<form #basicForm="ngForm" (ngSubmit)="submitData(basicForm.value)">
    <div>
        <input ngModel type="text" name="fname" placeholder="First Name" required> <br> <br>
    </div>
    <div>
        <input ngModel type="email" name="email" placeholder="Email"> <br> <br>
    </div>
    <div>
        <input ngModel type="password" name="pass" placeholder="Password"><br> <br>
    </div>
    <div>
        <button>Submit</button> <br> <br>
    </div>
</form>

<table border="2" *ngIf="showInfo">
    <tr>
        <td>{{ userData.fname }}</td>
        <td>{{ userData.email }}</td>
        <td>{{ userData.pass }}</td>
    </tr>
</table>
```

# Bootstrap

```console
==> app.component.ts
export class AppComponent {
  public isCollapsed = false;
}

==> app.component.html
<p>
    <ngb-alert [dismissible]="false">
        <strong>Warning!</strong> Better check yourself, you're not looking too good.
    </ngb-alert>
</p>

<p>
    <button type="button" class="btn btn-outline-primary" (click)="collapse.toggle()"
        [attr.aria-expanded]="!isCollapsed" aria-controls="collapseExample">
        Toggle with Function
    </button>
    <button type="button" class="btn btn-outline-primary ms-2" (click)="isCollapsed = ! isCollapsed"
        [attr.aria-expanded]="!isCollapsed" aria-controls="collapseExample">
        Toggle with Two Way Binding
    </button>
</p>
<div #collapse="ngbCollapse" [(ngbCollapse)]="isCollapsed">
    <div class="card">
        <div class="card-body">You can collapse this card by clicking one Toggle button</div>
    </div>
</div>
```

# Material UI
  - As we using Material UI in the app.component.html, so we have to add the material module in the app.module.ts file.
  - If we were to use standalone component, then we have to add the material module in its __.component.ts file 

```console
==> app.module.ts
import { MatButtonModule } from '@angular/material/button';
imports: [
  ...,
  MatButtonModule
]

==> app.component.html
<section>
    <div class="example-label">Basic</div>
    <div class="example-button-row">
        <button mat-raised-button>Basic</button>
        <button mat-raised-button color="primary">Primary</button>
        <button mat-raised-button color="accent">Accent</button>
        <button mat-raised-button color="warn">Warn</button>
        <button mat-raised-button disabled>Disabled</button>
        <a mat-raised-button href="https://www.google.com/" target="_blank">Link</a>
    </div>
</section>
```

# ToDo List Example

```console
==> app.component.ts
export class AppComponent {
  tasksList: any[] = [];
  addTask(task: string) {
    this.tasksList.push({ id: task.length, title: task });
  }
  delTask(id: number) {
    this.tasksList = this.tasksList.filter(task => task.id !== id);
  }
}

==> app.component.html
<!-- To Do List -->
<div class="container mt-5">
    <div class="row justify-content-center">
        <div class="col-md-6">
            <input type="text" class="form-control" name="task" placeholder="Enter Your Task Here" #task> <br>
            <div class="text-center">
                <button class="btn btn-dark" (click)="addTask(task.value)">
                    Add Task
                </button>
            </div>
        </div>
    </div>

    <div class="row justify-content-center mt-5">
        <div class="col-md-6">
            <ul class="list-group">
                <li class="list-group-item d-flex justify-content-between align-items-center"
                    *ngFor="let task of tasksList">
                    <span>{{ task.title }}</span>
                    <button class="btn btn-danger btn-sm" (click)="delTask(task.id)">
                        Del
                    </button>
                </li>
            </ul>
        </div>
    </div>
</div>
```

# Send Data from Parent to Child Component

```console
==> app.component.ts
export class AppComponent {
  data = 10;
  updateData() {
    this.data = Math.floor(Math.random() * 10);
  }
}

==> app.component.html
<div class="container mt-5">
    <div class="row">
        <div class="col-md-12">
            <app-child [item]="data"></app-child>

            <button (click)="updateData()" class="btn btn-dark">
                Update
            </button>
        </div>
    </div>
</div>

==> child.component.ts
import { Component, Input } from '@angular/core';

@Component({
  selector: 'app-child',
  templateUrl: './child.component.html',
  styleUrls: ['./child.component.css']
})

export class ChildComponent {
  @Input() item = 0;
}

==> child.component.html
<h1>Child {{ item }}</h1>
```