## TypeScript

TypeScript is a statically typed superset of JavaScript that compiles to plain JavaScript. It adds optional static typing, classes, interfaces, and other features to JavaScript, making it more robust and scalable for larger projects.

### Key Features

- **Static Typing**: TypeScript introduces static types to JavaScript, enabling type checking at compile-time and catching errors early in the development process.
- **Classes and Objects**: TypeScript supports object-oriented programming concepts such as classes, objects, inheritance, and interfaces.
- **Modules**: TypeScript provides built-in support for organizing code into modules, making it easier to manage dependencies and reuse code.
- **Generics**: Generics allow you to define reusable components that can work with different types.
- **Decorators**: TypeScript supports decorators, which provide a way to add metadata and modify the behavior of classes, methods, and properties.
- **Type Inference**: TypeScript can infer types based on the assigned values, reducing the need for explicit type annotations.
- **Tooling Support**: TypeScript integrates with various development tools and editors, offering features like autocompletion, code navigation, and refactoring.

## Data Types

This section provides an overview of the various data types used in the project. TypeScript supports static typing, which helps catch potential errors during development.

### 1. Primitives

- **Boolean**: Represents a logical value, either `true` or `false`.
- **Number**: Represents numeric values, both integers and floating-point numbers.
- **String**: Represents a sequence of characters enclosed in single or double quotes.
- **Null**: Represents the absence of a value.
- **Undefined**: Represents an uninitialized variable.
- **Symbol**: Represents a unique identifier that is immutable and can be used as an object key.

### 2. Arrays

- **Array**: Represents a collection of elements of a specific type. Arrays can be declared using the `Array<ElementType>` syntax or the `ElementType[]` syntax.

### 3. Objects

- **Object**: Represents a collection of key-value pairs. Objects can have properties with different data types.

### 4. Custom Types

- **Interfaces**: Interfaces define the structure of an object, specifying the names and types of its properties. They are useful for enforcing consistency and providing type-checking for objects.
- **Enums**: Enums allow you to define a set of named constants, providing a way to create a group of related values.
- **Type Aliases**: Type aliases allow you to create custom names for types, making your code more readable and maintainable.

### 5. Union Types

- **Union Types**: Union types allow a variable to have multiple types. They are denoted by the `|` symbol and provide flexibility in handling different possible value types.

### 6. Any

- **Any**: The `any` type allows variables to hold values of any type. It is useful when you don't have enough information about the type or when working with dynamic content.

## Examples


```typescript
// Example 1: Using primitive data types
let isActive: boolean = true;
let count: number = 10;
let name: string = "John Doe";

// Example 2: Defining an interface
interface Person {
  name: string;
  age: number;
}

let person: Person = {
  name: "Jane Smith",
  age: 25,
};

// Example 3: Using union types
let value: number | string = 42;
value = "hello";

// Example 4: Using type aliases
type ID = string | number;
let userId: ID = 123;
```



- **Primitives**: Boolean, Number, String, Null, Undefined, Symbol.
- **Arrays**: Array type represents a collection of elements of a specific type.
- **Objects**: Object type represents a collection of key-value pairs.
- **Tuples**: Tuple types allow expressing an array with a fixed number of elements, where each element may have a different type.
- **Enums**: Enum types allow defining a set of named constants.
- **Any**: Any type represents values of any type, useful for scenarios where type information is not known or when working with dynamic content.
- **Void**: Void type represents the absence of a value, commonly used for functions that do not return a value.
- **Never**: Never type represents a value that never occurs, typically used for functions that throw errors or have infinite loops.
- **Union Types**: Union types allow a variable to have multiple types.
- **Intersection Types**: Intersection types combine multiple types into one.

### Example 2

```typescript
// Example 1: Declaring variables with static types
let isActive: boolean = true;
let count: number = 10;
let name: string = "John Doe";

// Example 2: Defining interfaces
interface Person {
  name: string;
  age: number;
}

let person: Person = {
  name: "Jane Smith",
  age: 25,
};

// Example 3: Using classes and inheritance
class Animal {
  constructor(public name: string) {}

  speak(): void {
    console.log("Animal speaks");
  }
}

class Dog extends Animal {
  speak(): void {
    console.log("Dog barks");
  }
}

const dog: Dog = new Dog("Fido");
dog.speak(); // Output: Dog barks

// Example 4: Using generics
function identity<T>(arg: T): T {
  return arg;
}

let result = identity<string>("hello");
console.log(result); // Output: hello

// Example 5: Using decorators
function log(target: any, key: string) {
  console.log(`Method ${key} is decorated.`);
}

class ExampleClass {
  @log
  greet() {


    console.log("Hello, world!");
  }
}

const instance = new ExampleClass();
instance.greet(); // Output: Method greet is decorated. Hello, world!
```
