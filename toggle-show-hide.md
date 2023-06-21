
Component code (`my-component.component.ts`):
```typescript
export class MyComponent {
  showElement: boolean = true;

  toggleElement() {
    this.showElement = !this.showElement;
  }
}
```

Template code (`my-component.component.html`):
```html
<button (click)="toggleElement()">Toggle Element</button>

<div [hidden]="showElement">
  <p>This element is hidden.</p>
</div>

<div [hidden]="!showElement">
  <p>This element is visible.</p>
</div>
```

Explanation:
- We have a boolean property `showElement` in the component that determines whether the element should be shown or hidden. It is initially set to `true`.
- The `(click)` event on the "Toggle Element" button triggers the `toggleElement` method, which toggles the value of `showElement` using `this.showElement = !this.showElement`.
- The first `<div>` element uses `[hidden]="showElement"` to conditionally hide the element if `showElement` is `true`. When `showElement` is `true`, the element will be hidden.
- The second `<div>` element uses `[hidden]="!showElement"` to conditionally hide the element if `showElement` is `false`. When `showElement` is `false`, the element will be hidden.
- By using the `[hidden]` attribute binding with the appropriate conditions, the elements are hidden or shown based on the value of `showElement`.
