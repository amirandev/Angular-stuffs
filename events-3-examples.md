To demonstrate applying styles and other actions on click in Angular, here are some examples:

**Applying Styles on Click:**

1. In your component TypeScript file (e.g., `my-component.component.ts`), define a property to track the click state and another property for dynamic styling:
   ```typescript
   import { Component } from '@angular/core';

   @Component({
     selector: 'app-my-component',
     templateUrl: './my-component.component.html',
     styleUrls: ['./my-component.component.css']
   })
   export class MyComponentComponent {
     isClicked = false;
     dynamicStyle = {};

     handleClick() {
       this.isClicked = true;
       this.dynamicStyle = {
         'background-color': 'red',
         'color': 'white',
         'font-size': '20px'
       };
     }
   }
   ```
   In this example, `isClicked` tracks the click state, and `dynamicStyle` stores the CSS properties for dynamic styling.

2. In your component HTML file (e.g., `my-component.component.html`), apply the dynamic style based on the click event:
   ```html
   <div [ngStyle]="dynamicStyle" (click)="handleClick()">Click me to apply style</div>
   ```
   The `ngStyle` directive binds the `dynamicStyle` object to the `style` attribute of the `<div>` element. The `(click)` event triggers the `handleClick()` method when the div is clicked.

**Other Actions on Click:**

1. In your component TypeScript file, define a property or invoke a method to perform the desired action on click:
   ```typescript
   import { Component } from '@angular/core';

   @Component({
     selector: 'app-my-component',
     templateUrl: './my-component.component.html',
     styleUrls: ['./my-component.component.css']
   })
   export class MyComponentComponent {
     counter = 0;

     incrementCounter() {
       this.counter++;
     }

     resetCounter() {
       this.counter = 0;
     }
   }
   ```
   In this example, `counter` is a property that can be incremented or reset.

2. In your component HTML file, trigger the desired action on click using event binding:
   ```html
   <button (click)="incrementCounter()">Increment Counter</button>
   <button (click)="resetCounter()">Reset Counter</button>
   ```
   The `(click)` event binding calls the corresponding methods `incrementCounter()` or `resetCounter()` when the buttons are clicked.

By following these examples, you can apply styles dynamically and perform other actions when an element is clicked in your Angular application.
