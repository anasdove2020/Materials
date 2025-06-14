# 7 JavaScript Concepts to Master Before React 

Table of contents:
1. Arrow Functions
2. Map and Filter
3. Slice() and Splice()
4. Destructuring
5. Rest and Spread Operators
6. Template Literals
7. Promises and Async/Await

## 1. Arrow Functions 

Arrow function provide a concise way to write function expressions. 

```
const greet = name => 'Hello, ${name}!';
console.log(greet('React Developer'));
```

## 2. Map and Filter 

Map creates a new array by transforming each element, while Filter creates a new array with elements that pass a test.

```
const numbers = [1, 2, 3, 4, 5];
const doubled = numbers.map(num => num * 2);
const evens = numbers,filter(num => num % 2 === 0);
```

## 3. Slice() and Splice()

Slice() returns a shallow copy of a portion of an array. Splice() changes the contents of an array by removing or replacing existing elements and/or adding new elements.

```
const fruits = ['apple', 'banana', 'cherry', 'date'];
const a = fruits.slice(1, 3);

// ['banana', 'cherry']

const b = fruits.splice(1, 2, 'strawberry');

//

```

## 4. Destructuring

Destructuring allows you to extract values from objects or arrays into distict variables.

```
const person = { name: 'John', age: 30, job: 'Developer' }

const { name, age } = person
```

## 5. Rest and Spread Operators

The rest operator collects multiple element into an array. The spread operator expands an iterable into individual elements.

```
// Rest Operator
const sum = (...numbers) => numbers.reduce((acc, num) => acc + num, 0)

// Spread Operator

const arr1 = [1, 2, 3];
const arr2 = [4, 5, 6];

const combined = [...arr1, ...arr2]
```

## 6. Template Literals

Template Literals allow embedded expressions and multi-line strings.

```
const name = 'React';
const version = 18;
const greeting = `Hello, ${name}! You are using version ${version}`;
```

## 7. Promised and async/await

Promises and async/await are used for handling asyncronous operations.

```
const fetchData = () => {
  return new Promise(resolve => {
    setTimeout(() => resolve('Data fetched !'), 2000);
  })
}

async function getData() {
  const result = await fetchData();
}
```
