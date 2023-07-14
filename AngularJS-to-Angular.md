Here's the documentation for the Angular directives along with examples and explanations, based on the latest version of Angular.

1. **ng-app**: In Angular, you bootstrap your application manually in the main module file (`app.module.ts`). You define the root component using the `bootstrap` method. Here's an example:

   ```typescript
   import { NgModule } from '@angular/core';
   import { BrowserModule } from '@angular/platform-browser';
   import { AppComponent } from './app.component';

   @NgModule({
     imports: [BrowserModule],
     declarations: [AppComponent],
     bootstrap: [AppComponent]
   })
   export class AppModule { }
   ```

2. **ng-init**: Angular doesn't have an equivalent directive. Instead, you can initialize variables and perform actions in the component's constructor or `ngOnInit` lifecycle hook. Here's an example:

   ```typescript
   import { Component, OnInit } from '@angular/core';

   @Component({
     selector: 'app-root',
     template: `
       <h1>{{ title }}</h1>
       <p>Initialized count: {{ count }}</p>
     `
   })
   export class AppComponent implements OnInit {
     title: string;
     count: number;

     constructor() {
       this.title = 'My Angular App';
     }

     ngOnInit() {
       this.count = 0;
     }
   }
   ```

3. **ng-model**: Angular provides two approaches for handling form controls: Reactive Forms and Template-driven Forms. In Reactive Forms, you use the `FormControl` class to bind form controls to component properties. In Template-driven Forms, you can use `ngModel` to achieve two-way data binding. Here's an example using Template-driven Forms:

   ```html
   <input [(ngModel)]="name" type="text">
   <p>Entered Name: {{ name }}</p>
   ```

4. **ng-bind**: In Angular, you can use interpolation (`{{ expression }}`) to bind expressions directly in the template. Here's an example:

   ```html
   <p>Hello, {{ name }}!</p>
   ```

5. **ng-class**: Angular provides the `ngClass` directive to dynamically add or remove CSS classes based on conditions. You can bind it to an expression that evaluates to an object or an array of class names. Here's an example:

   ```html
   <div [ngClass]="{ 'highlight': isHighlighted, 'bold': isBold }">Some text</div>
   ```

6. **ng-controller**: Angular uses components instead of controllers. Components encapsulate the behavior and properties of a particular view. Here's an example of a component:

   ```typescript
   import { Component } from '@angular/core';

   @Component({
     selector: 'app-example',
     template: `
       <h2>{{ title }}</h2>
       <p>{{ description }}</p>
     `
   })
   export class ExampleComponent {
     title = 'Example Component';
     description = 'This is an example component.';
   }
   ```

7. **ng-repeat**: In Angular, you use the `ngFor` directive to iterate over an array or collection and generate HTML elements dynamically. Here's an example:

   ```html
   <ul>
     <li *ngFor="let item of items">{{ item }}</li>
   </ul>
   ```

8. **ng-show**: In Angular, you can use the `ngIf` directive to conditionally render or remove an element from the DOM. If the expression evaluates to true, the element is rendered; otherwise, it is removed. Here's an example:

   ```html
   <div *ngIf="showElement">This element is shown.</div>
   ```

9. **ng-hide**: In Angular, you can achieve the equivalent of `ng-hide` by using the `ngIf` directive with the negation operator (`*ngIf="!expression"`). Here's an example:

   ```html
   <div *ngIf="!hideElement">This element is not hidden.</div>
   ```

10. **ng-switch**: Angular provides the `ngSwitch` directive for conditional rendering of HTML content based on multiple cases. You use it with `ngSwitchCase` and `ngSwitchDefault` to define the cases. Here's an example:

    ```html
    <div [ngSwitch]="condition">
      <p *ngSwitchCase="'A'">Case A content</p>
      <p *ngSwitchCase="'B'">Case B content</p>
      <p *ngSwitchDefault>Default case content</p>
    </div>
    ```

11. **ng-view**: Angular uses the Angular Router module for handling routing and views. You define routes in the main module file and use the `router-outlet` directive as a placeholder where different views are dynamically loaded based on the current route. Here's an example:

    ```typescript
    import { NgModule } from '@angular/core';
    import { BrowserModule } from '@angular/platform-browser';
    import { RouterModule, Routes } from '@angular/router';
    import { HomeComponent } from './home.component';
    import { AboutComponent } from './about.component';

    const routes: Routes = [
      { path: '', component: HomeComponent },
      { path: 'about', component: AboutComponent }
    ];

    @NgModule({
      imports: [BrowserModule, RouterModule.forRoot(routes)],
      declarations: [HomeComponent, AboutComponent],
      bootstrap: [AppComponent]
    })
    export class AppModule { }
    ```

    ```html
    <router-outlet></router-outlet>
    ```

12. **ng-click**: In Angular, you can use the `(click)` event binding to execute a function or expression when an element is clicked. Here's an example:

    ```html
    <button (click)="onClick()">Click me!</button>
    ```

    ```typescript
    import { Component } from '@angular/core';

    @Component({
      selector: 'app-example',
      template: `
        <button (click)="onClick()">Click me!</button>
      `
    })
    export class ExampleComponent {
      onClick() {
        console.log('Button clicked!');
      }
    }
    ```

13. **ng-if**: Angular's `ngIf` directive is used to conditionally render or remove an element from the DOM based on an expression's truthiness. Here's an example:

    ```html
    <div *ngIf="condition">This element is shown.</div>
    ```
    
14. **JSON**: Angular provides the `json` pipe to format JavaScript objects as JSON strings. It can be used to display JSON data in a readable format. Here's an example:

   ```html
   <pre>{{ jsonData | json }}</pre>
   ```

   ```typescript
   import { Component } from '@angular/core';

   @Component({
     selector: 'app-example',
     template: `
       <pre>{{ jsonData | json }}</pre>
     `
   })
   export class ExampleComponent {
     jsonData = { name: 'John Doe', age: 30, city: 'New York' };
   }
   ```

15. **limitTo**: Angular provides the `slice` pipe to limit the number of items displayed in an array or string. It is commonly used to truncate or filter lists. Here's an example:

   ```html
   <ul>
     <li *ngFor="let item of items | slice:0:5">{{ item }}</li>
   </ul>
   ```

16. **orderBy**: Angular does not provide an `orderBy` directive by default. However, you can create a custom pipe or use a third-party library like Lodash to achieve sorting functionality. Here's an example using Lodash:

   First, install Lodash:

   ```shell
   npm install lodash
   ```

   Then, import the necessary functions and use them in a custom pipe:

   ```typescript
   import { Pipe, PipeTransform } from '@angular/core';
   import { orderBy } from 'lodash';

   @Pipe({ name: 'orderBy' })
   export class OrderByPipe implements PipeTransform {
     transform(array: any[], field: string, order: 'asc' | 'desc' = 'asc'): any[] {
       return orderBy(array, field, order);
     }
   }
   ```

   Finally, use the custom pipe in your template:

   ```html
   <ul>
     <li *ngFor="let item of items | orderBy:'name':'asc'">{{ item.name }}</li>
   </ul>
   ```

   ```typescript
   import { Component } from '@angular/core';

   @Component({
     selector: 'app-example',
     template: `
       <ul>
         <li *ngFor="let item of items | orderBy:'name':'asc'">{{ item.name }}</li>
       </ul>
     `
   })
   export class ExampleComponent {
     items = [
       { name: 'John', age: 30 },
       { name: 'Alice', age: 25 },
       { name: 'Bob', age: 35 }
     ];
   }
   ```
