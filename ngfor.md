Create a new component file (`example.component.ts`) and add the following code:

```typescript
import { Component } from '@angular/core';

@Component({
  selector: 'app-example',
  templateUrl: './example.component.html',
})
export class ExampleComponent {
  items: string[] = ['Item 1', 'Item 2', 'Item 3'];
}
```

Create a new template file (`example.component.html`) in the same directory and add the following code:

```html
<ul>
  <li *ngFor="let item of items">{{ item }}</li>
</ul>
```
