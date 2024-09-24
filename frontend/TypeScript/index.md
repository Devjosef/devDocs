# TypeScript

## Introduction
TypeScript is a strongly typed programming language that builds on JavaScript, giving you better tooling at any scale. It provides static type definitions, which help catch errors early during development.

## Basic Syntax
```typescript
// Variable declaration with type
let isDone: boolean = false;

// Function with typed parameters and return type
function add(x: number, y: number): number {
    return x + y;
}

// Interface
interface Person {
    firstName: string;
    lastName: string;
}

// Function using an interface
function greet(person: Person) {
    return `Hello, ${person.firstName} ${person.lastName}`;
}

let user = { firstName: "John", lastName: "Doe" };
console.log(greet(user));
````


## Common Use Cases
- Large-scale JavaScript applications
- Projects requiring static type checking
- Codebases that need to be more maintainable and scalable

## Advanced Features
- **Generics**: Create reusable components that work with any data type.
- **Decorators**: Special kind of declaration that can be attached to a class, method, accessor, property, or parameter.
- **Type Inference**: Automatically infer types based on the values assigned.
- **Modules**: Organize code into reusable pieces.

## Code Snippets
### Generics
````typescript
function identity<T>(arg: T): T {
    return arg;
}

let output = identity<string>("myString");
````


### Decorators
````typescript
function sealed(constructor: Function) {
    Object.seal(constructor);
    Object.seal(constructor.prototype);
}

@sealed
class Greeter {
    greeting: string;
    constructor(message: string) {
        this.greeting = message;
    }
    greet() {
        return `Hello, ${this.greeting}`;
    }
}
````


### Type Inference
````typescript
let x = 3; // inferred as number
let y = "hello"; // inferred as string
````


### Modules
````typescript
// math.ts
export function add(x: number, y: number): number {
    return x + y;
}

// app.ts
import { add } from './math';
console.log(add(2, 3));
````


## Tips & Best Practices
- **Use Interfaces and Types**: Define object shapes and function signatures.
- **Enable Strict Mode**: Use `strict` mode in `tsconfig.json` for better type safety.
- **Type Annotations**: Use type annotations to make the code more readable and maintainable.
- **Avoid `any`**: Avoid using the `any` type as much as possible to maintain type safety.
- **Regular Updates**: Keep TypeScript updated to leverage new features and improvements.

## External Resources
- [TypeScript Official Documentation](https://www.typescriptlang.org/docs/)
- [TypeScript Deep Dive](https://basarat.gitbook.io/typescript/)
- [TypeScript Handbook](https://www.typescriptlang.org/docs/handbook/intro.html)
- [DefinitelyTyped](https://definitelytyped.org/)