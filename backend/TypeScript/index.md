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
- Building scalable web applications
- Developing Node.js applications
- Creating libraries and frameworks
- Enhancing JavaScript projects with static types

## Advanced Features
- **Generics**: Create reusable components with flexible types.
- **Decorators**: Add metadata to classes and methods.
- **Modules**: Organize code into reusable modules.
- **Type Inference**: Automatically infer types to reduce boilerplate.

## Code Snippets
### Using Generics
```typescript
function identity<T>(arg: T): T {
    return arg;
}

let output = identity<string>("myString");
````


### Using Decorators
```typescript
function log(target: any, key: string) {
    let value = target[key];

    const getter = () => {
        console.log(`Get: ${key} => ${value}`);
        return value;
    };

    const setter = (newVal) => {
        console.log(`Set: ${key} => ${newVal}`);
        value = newVal;
    };

    Object.defineProperty(target, key, {
        get: getter,
        set: setter,
        enumerable: true,
        configurable: true,
    });
}

class Person {
    @log
    public name: string;

    constructor(name: string) {
        this.name = name;
    }
}

const p = new Person("John");
p.name = "Doe";
````


### Using Modules
```typescript
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

