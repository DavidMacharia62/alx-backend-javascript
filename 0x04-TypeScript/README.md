# TypeScript Fundamentals Readme

This readme provides a comprehensive guide to the basic types in TypeScript, interfaces, classes, functions, working with the DOM, generic types, namespaces, merging declarations, using ambient namespaces to import external libraries, and basic nominal typing in TypeScript.

## Table of Contents

1. [Basic Types](#basic-types)
2. [Interfaces, Classes, and Functions](#interfaces-classes-and-functions)
3. [Working with the DOM and TypeScript](#working-with-the-dom-and-typescript)
4. [Generic Types](#generic-types)
5. [Namespaces](#namespaces)
6. [Merging Declarations](#merging-declarations)
7. [Using Ambient Namespace to Import External Library](#using-ambient-namespace-to-import-external-library)
8. [Basic Nominal Typing with TypeScript](#basic-nominal-typing-with-typescript)

## Basic Types

TypeScript includes a set of basic types such as `number`, `string`, `boolean`, `null`, `undefined`, `symbol`, and `object`. Additionally, TypeScript supports arrays (`Array<type>`) and tuples for defining fixed-size arrays.

Example:
```typescript
let num: number = 42;
let str: string = "Hello, TypeScript!";
let bool: boolean = true;
let arr: number[] = [1, 2, 3];
let tuple: [string, number] = ["TypeScript", 3];
```

## Interfaces, Classes, and Functions

### Interfaces
Interfaces allow you to define the structure of an object. They provide a blueprint for the shape of the data.

Example:
```typescript
interface Person {
  name: string;
  age: number;
}

const person: Person = { name: "John", age: 25 };
```

### Classes
Classes help in creating objects with methods and properties.

Example:
```typescript
class Animal {
  constructor(public name: string) {}

  makeSound() {
    console.log("Some generic sound");
  }
}

const cat = new Animal("Whiskers");
cat.makeSound();
```

### Functions
Functions in TypeScript can have defined input and output types.

Example:
```typescript
function add(x: number, y: number): number {
  return x + y;
}

const result: number = add(3, 5);
```

## Working with the DOM and TypeScript

TypeScript allows for strongly-typed interactions with the DOM. Use type assertions or type definitions for DOM elements.

Example:
```typescript
const element = document.getElementById("myElement") as HTMLInputElement;
element.value = "Hello, DOM!";
```

## Generic Types

Generics allow you to create flexible and reusable components that work with a variety of data types.

Example:
```typescript
function identity<T>(arg: T): T {
  return arg;
}

const result = identity<string>("TypeScript");
```

## Namespaces

Namespaces help in organizing code by encapsulating related functionality.

Example:
```typescript
namespace Geometry {
  export interface Point {
    x: number;
    y: number;
  }

  export function distance(p1: Point, p2: Point): number {
    // Implementation
  }
}

const point1: Geometry.Point = { x: 0, y: 0 };
const point2: Geometry.Point = { x: 3, y: 4 };
const dist = Geometry.distance(point1, point2);
```

## Merging Declarations

TypeScript allows merging of declarations for functions, interfaces, and classes.

Example:
```typescript
interface User {
  name: string;
}

interface User {
  age: number;
}

const user: User = { name: "John", age: 25 };
```

## Using Ambient Namespace to Import External Library

When using external libraries without TypeScript definitions, declare an ambient namespace.

Example:
```typescript
declare namespace MyLibrary {
  function greet(name: string): void;
}

MyLibrary.greet("World");
```

## Basic Nominal Typing with TypeScript

Nominal typing involves creating distinct types even if their structures are identical.

Example:
```typescript
class AccountId {
  private id: string;

  constructor(id: string) {
    this.id = id;
  }
}

function transfer(from: AccountId, to: AccountId, amount: number) {
  // Implementation
}

const sender = new AccountId("123");
const receiver = new AccountId("456");

transfer(sender, receiver, 100);
```

Feel free to explore each section for detailed explanations and examples. Happy coding with TypeScript!
