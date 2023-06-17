1. Create a component using the Angular CLI command `ng generate component header`. This will generate the necessary files for your component.

2. In the parent component's template file (e.g., `parent.component.html`), use the component selector to include the child component and pass parameters using property binding.

   ```html
   <app-header [param1]="value1" [param2]="value2"></app-header>
   ```

   Here, `app-header` is the selector of the child component, and `param1` and `param2` are properties in the child component that will receive the values `value1` and `value2`, respectively.

3. In the child component's TypeScript file (e.g., `header.component.ts`), define the input properties using the `@Input` decorator.

   ```typescript
   import { Component, Input } from '@angular/core';

   @Component({
     selector: 'app-header',
     templateUrl: './header.component.html',
     styleUrls: ['./header.component.css']
   })
   export class HeaderComponent {
     @Input() param1: string;
     @Input() param2: number;
   }
   ```

   The `@Input` decorator allows the child component to receive values from its parent component.

4. Use the received values in the child component's template file (e.g., `header.component.html`).

   ```html
   <h1>Parameter 1: {{ param1 }}</h1>
   <p>Parameter 2: {{ param2 }}</p>
   ```

   Here, `param1` and `param2` are the received properties from the parent component, and you can use them within the child component's template.
