
1. Create a new component file (`example.component.ts`) and add the following code:

```typescript
import { Component } from '@angular/core';

@Component({
  selector: 'app-example',
  templateUrl: './example.component.html',
})
export class ExampleComponent {
  showItem: boolean = true;
}
```

2. Create a new template file (`example.component.html`) in the same directory and add the following code:

```html
<div *ngIf="showItem">
  <p>This item is visible when showItem is true.</p>
</div>

<div *ngIf="!showItem">
  <p>This item is visible when showItem is false.</p>
</div>
```
