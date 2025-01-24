# Closures in JavaScript

A **closure** is a combination of a function and its lexical environment (the scope in which it was created). Closures allow functions to access variables from their outer scope even after the outer function has finished executing.

---

## Key Characteristics

1. **Lexical Scoping**:
   - Functions remember the scope in which they were defined, not where they are executed.
2. **Access to Outer Variables**:
   - A closure allows access to variables in the parent function's scope, even after the parent function has returned.

---

## Basic Example of a Closure

**Example**:
```js
function outerFunction() {
  let outerVariable = 'I am from outer scope';

  return function innerFunction() {
    console.log(outerVariable);
  };
}

const myClosure = outerFunction();
myClosure(); // Output: I am from outer scope
```
---

## Practical Use Cases of Closures

### 1. **Data Encapsulation**
- Closures can create private variables that are not accessible from the outside.

**Example**:
```js
function counter() {
  let count = 0;

  return {
    increment() {
      count++;
      console.log(count);
    },
    decrement() {
      count--;
      console.log(count);
    },
  };
}

const myCounter = counter();
myCounter.increment(); // 1
myCounter.increment(); // 2
myCounter.decrement(); // 1
```
---

### 2. **Function Factories**
- Closures are useful for creating functions dynamically with specific configurations.

**Example**:
```js
function multiplier(factor) {
  return function (number) {
    return number * factor;
  };
}

const double = multiplier(2);
const triple = multiplier(3);

console.log(double(5)); // 10
console.log(triple(5)); // 15
```
---

### 3. **Callback Functions**
- Closures help maintain state in asynchronous operations.

**Example**:
```js
function fetchData(url) {
  return function (callback) {
    console.log(`Fetching data from ${url}`);
    callback();
  };
}

const fetchFromAPI = fetchData('https://api.example.com');
fetchFromAPI(() => console.log('Data fetched!'));
// Output:
// Fetching data from https://api.example.com
// Data fetched!
```

---

## Common Interview Questions

1. **What is a closure in JavaScript?**
   - A closure is when a function remembers its lexical scope, even when executed outside that scope.

2. **Can you give an example of a practical use case for closures?**
   - Data encapsulation, such as creating private variables in a counter or configuration-specific functions like a multiplier.

3. **How do closures work with asynchronous functions?**
   - Closures enable asynchronous functions to remember the variables of their outer scope.

---

## Key Points to Remember

1. Closures allow inner functions to access variables from their outer scope.
2. Even after the outer function has returned, the closure retains access to its lexical environment.
3. Overuse of closures may lead to performance issues due to retained memory, so use them judiciously.
