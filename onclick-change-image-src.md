Component code (`my-component.component.ts`):
```typescript
export class MyComponent {
  imageUrl: string = '';

  updateImageSrc(url: string) {
    this.imageUrl = url;
  }
}
```

Template code (`my-component.component.html`):
```html
<button (click)="updateImageSrc('https://example.com/image.jpg')">Change Image</button>

<img [src]="imageUrl" alt="Image">
```

Explanation:
- We have a property `imageUrl` in the component that holds the current image URL.
- The `updateImageSrc` function is called when the "Change Image" button is clicked. It takes an image URL as a parameter and assigns it to `this.imageUrl`.
- The `<img>` element's `src` attribute is bound to the `imageUrl` property using `[src]="imageUrl"`. This means that when `imageUrl` is updated, the `src` attribute of the `<img>` element will reflect the new value.
