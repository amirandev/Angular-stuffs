Example 1: Live Writing with Input Event
In this example, we'll bind an input field to a component property and update it in real-time using the input event.

Component code (`my-component.component.ts`):
```typescript
export class MyComponent {
  inputValue: string = '';

  handleInputChange(event: Event) {
    this.inputValue = (event.target as HTMLInputElement).value;
  }
}
```

Template code (`my-component.component.html`):
```html
<input type="text" (input)="handleInputChange($event)" [value]="inputValue">
<p>Input value: {{ inputValue }}</p>
```

Explanation:
- We bind the `(input)` event of the input field to the `handleInputChange` method, passing `$event` as the parameter.
- Inside the `handleInputChange` method, we extract the input value from the event and assign it to the `inputValue` property of the component.
- The `[value]` attribute on the input field binds the `inputValue` property to keep it in sync with the input field's value.
- The input value is displayed in real-time using interpolation (`{{ inputValue }}`) within the `<p>` tag.

Example 2: Increase/Decrease Number in Template
In this example, we'll implement functionality to increase or decrease a number displayed in the template.

Component code (`my-component.component.ts`):
```typescript
export class MyComponent {
  counter: number = 0;

  increase() {
    this.counter++;
  }

  decrease() {
    this.counter--;
  }
}
```

Template code (`my-component.component.html`):
```html
<p>Counter: {{ counter }}</p>
<button (click)="increase()">Increase</button>
<button (click)="decrease()">Decrease</button>
```

Explanation:
- The `counter` property is initialized to 0 in the component.
- Clicking the "Increase" button triggers the `increase` method, which increments the `counter` property by 1.
- Clicking the "Decrease" button triggers the `decrease` method, which decrements the `counter` property by 1.
- The current value of `counter` is displayed using interpolation (`{{ counter }}`) within the `<p>` tag.
