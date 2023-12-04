# README: Working with Arrays and Data Structures in JavaScript

## Table of Contents
1. [Introduction](#introduction)
2. [Working with Arrays](#working-with-arrays)
    - [Map](#map)
    - [Filter](#filter)
    - [Reduce](#reduce)
3. [Typed Arrays](#typed-arrays)
4. [Set, Map, and WeakMap Data Structures](#set-map-and-weakmap-data-structures)

---

## 1. Introduction <a name="introduction"></a>

This README provides an overview and detailed instructions on how to use some essential JavaScript features for working with arrays and various data structures.

## 2. Working with Arrays <a name="working-with-arrays"></a>

### Map <a name="map"></a>

The `map` function is used to transform each element of an array according to a provided function. It creates a new array with the results of applying the provided function to each element of the original array.

#### Usage:

```javascript
const originalArray = [1, 2, 3, 4, 5];

const mappedArray = originalArray.map((element) => element * 2);

console.log(mappedArray); // Output: [2, 4, 6, 8, 10]
```

### Filter <a name="filter"></a>

The `filter` function is used to create a new array with all elements that pass the test implemented by the provided function.

#### Usage:

```javascript
const originalArray = [1, 2, 3, 4, 5];

const filteredArray = originalArray.filter((element) => element % 2 === 0);

console.log(filteredArray); // Output: [2, 4]
```

### Reduce <a name="reduce"></a>

The `reduce` function is used to apply a function to each element of the array (from left to right) to reduce it to a single value.

#### Usage:

```javascript
const originalArray = [1, 2, 3, 4, 5];

const sum = originalArray.reduce((accumulator, currentValue) => accumulator + currentValue, 0);

console.log(sum); // Output: 15
```

## 3. Typed Arrays <a name="typed-arrays"></a>

JavaScript provides a set of built-in objects called **Typed Arrays** which allow you to work with raw binary data. They are especially useful when dealing with tasks like handling data from network protocols or interacting with WebGL.

#### Example:

```javascript
// Creating a typed array of 8-bit integers
const int8Array = new Int8Array([1, 2, 3, 4, 5]);

console.log(int8Array); // Output: Int8Array [1, 2, 3, 4, 5]
```

Typed Arrays come in various types such as Int8Array, Uint8Array, Int16Array, Float32Array, etc., each corresponding to different data types.

## 4. Set, Map, and WeakMap Data Structures <a name="set-map-and-weakmap-data-structures"></a>

### Set

The `Set` object lets you store unique values of any type. It's iterable, and the order of elements is maintained.

#### Example:

```javascript
const uniqueNumbers = new Set([1, 2, 3, 3, 4, 5]);

console.log(uniqueNumbers); // Output: Set { 1, 2, 3, 4, 5 }
```

### Map

The `Map` object holds key-value pairs and remembers the original insertion order of the keys.

#### Example:

```javascript
const myMap = new Map();

myMap.set('key1', 'value1');
myMap.set('key2', 'value2');

console.log(myMap.get('key1')); // Output: value1
```

### WeakMap

The `WeakMap` object is a collection of key-value pairs where the keys must be objects, and the values can be arbitrary values. WeakMaps are "weak" in the sense that they don't prevent garbage collection of the keys.

#### Example:

```javascript
let weakMap = new WeakMap();

let obj = {};
weakMap.set(obj, "some value");

console.log(weakMap.get(obj)); // Output: "some value"
```

---

Feel free to explore and integrate these features into your JavaScript projects. Understanding these concepts will empower you to write more efficient and expressive code. If you have any questions or need further clarification, refer to the official [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript) for detailed information on JavaScript features and functionalities.
