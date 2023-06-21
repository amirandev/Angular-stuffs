Template code (`my-component.component.html`):
```html
<div (click)="handleClick($event)">
  <button id="myButton" data-custom-attribute="custom-value">Click Me</button>
</div>
```

Component code (`my-component.component.ts`):
```typescript
export class MyComponent {
  handleClick(event: MouseEvent) {
    const target = event.target as HTMLElement;
    const customAttribute = target.getAttribute('data-custom-attribute');
    console.log(customAttribute);
  }
}
```

Explanation:
- We have a `<div>` container with a `<button>` inside it.
- The `(click)` event handler is attached to the `<div>` element, triggering the `handleClick` function when clicked.
- Inside the `handleClick` function, the `event.target` represents the clicked element (`<button>` in this case). We cast it to `HTMLElement` to access its methods.
- Using the `getAttribute()` method, we retrieve the value of the `data-custom-attribute` attribute from the clicked element.
- Finally, we log the value of the custom attribute to the console.
