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


