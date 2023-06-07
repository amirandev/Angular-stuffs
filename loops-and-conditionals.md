Certainly! Here are full examples showcasing loops and conditional statements (switch cases) in Angular:

**Loops in Angular:**

1. Using `ngFor` Directive:
   ```html
   <ul>
     <li *ngFor="let item of items">{{ item }}</li>
   </ul>
   ```
   Component:
   ```typescript
   import { Component } from '@angular/core';

   @Component({
     selector: 'app-my-component',
     templateUrl: './my-component.component.html',
     styleUrls: ['./my-component.component.css']
   })
   export class MyComponentComponent {
     items = ['Apple', 'Banana', 'Orange'];
   }
   ```
   In this example, an array `items` is created in the component, and the `*ngFor` directive is used to loop through the array and generate `<li>` elements for each item.

2. Using Index in Loop:
   ```html
   <ul>
     <li *ngFor="let item of items; index as i">{{ i + 1 }}. {{ item }}</li>
   </ul>
   ```
   Component:
   ```typescript
   import { Component } from '@angular/core';

   @Component({
     selector: 'app-my-component',
     templateUrl: './my-component.component.html',
     styleUrls: ['./my-component.component.css']
   })
   export class MyComponentComponent {
     items = ['Apple', 'Banana', 'Orange'];
   }
   ```
   In this example, the `index as i` syntax is used to access the index of each item in the loop, and `{{ i + 1 }}` is used to display the index incremented by 1.

**Conditional Statements (Switch Cases) in Angular:**

1. Using `ngSwitch` Directive:
   ```html
   <div [ngSwitch]="color">
     <p *ngSwitchCase="'red'">This is red.</p>
     <p *ngSwitchCase="'blue'">This is blue.</p>
     <p *ngSwitchCase="'green'">This is green.</p>
     <p *ngSwitchDefault>Color not found.</p>
   </div>
   ```
   Component:
   ```typescript
   import { Component } from '@angular/core';

   @Component({
     selector: 'app-my-component',
     templateUrl: './my-component.component.html',
     styleUrls: ['./my-component.component.css']
   })
   export class MyComponentComponent {
     color = 'blue';
   }
   ```
   In this example, the `color` variable in the component determines which case to display using the `ngSwitch` directive. If the `color` matches any of the cases, the corresponding content is rendered. Otherwise, the default case is displayed.

2. Using `ngIf` Directive for Conditional Rendering:
   ```html
   <div *ngIf="isLogged">Welcome, user!</div>
   ```
   Component:
   ```typescript
   import { Component } from '@angular/core';

   @Component({
     selector: 'app-my-component',
     templateUrl: './my-component.component.html',
     styleUrls: ['./my-component.component.css']
   })
   export class MyComponentComponent {
     isLogged = true;
   }
   ```
   In this example, the `*ngIf` directive is used to conditionally render the `<div>` element based on the value of the `isLogged` variable in the component.

3. Using Ternary Operator:
   ```html
   <div>{{ isLoggedIn ? 'Welcome, user!' : 'Please log in.' }}</div>
   ```
   Component:
   ```typescript
   import { Component } from '@angular/core';

   @Component({
     selector: 'app-my-component',
    

 templateUrl: './my-component.component.html',
     styleUrls: ['./my-component.component.css']
   })
   export class MyComponentComponent {
     isLoggedIn = true;
   }
   ```
   In this example, the ternary operator (`? :`) is used within the template expression to conditionally display either `'Welcome, user!'` or `'Please log in.'` based on the value of the `isLoggedIn` variable.

By following these examples, you can effectively utilize loops and conditional statements in your Angular application.
