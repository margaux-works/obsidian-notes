# Object Literals in JavaScript

Object literals are a convenient way to create and initialize objects in JavaScript. They are widely used for structuring data, encapsulating functionality, and creating configurations.

---

## Key Features of Object Literals

1. **Simple Syntax**:
   - Use curly braces `{}` to define an object and include key-value pairs.

**Example**:
```js
const person = {
  name: 'Alice',
  age: 30,
  greet: function () {
    console.log(`Hello, my name is ${this.name}.`);
  },
};

person.greet(); // Output: Hello, my name is Alice.
```
---

## ES6 Enhancements to Object Literals

### **Property Shorthand**
- If the property name matches the variable name, you can use shorthand to define the object.

**Before ES6**:
```js
const name = 'Bob';
const age = 25;

const person = {
  name: name,
  age: age,
};
```
**With ES6**:
```js
const name = 'Bob';
const age = 25;

const person = {
  name,
  age,
};

console.log(person); // { name: 'Bob', age: 25 }
```

---

### **Method Shorthand**
- You can define methods in object literals without using the `function` keyword.

**Before ES6**:
```js
const person = {
  greet: function () {
    console.log('Hello!');
  },
};
```
**With ES6**:
```js
const person = {
  greet() {
    console.log('Hello!');
  },
};
```
---

### **Computed Property Names**
- You can dynamically define property names using expressions in square brackets (`[]`).

**Example**:
```js
const day = 'Monday';
const openingHours = {
  [day]: {
    open: 9,
    close: 17,
  },
};

console.log(openingHours); // { Monday: { open: 9, close: 17 } }
```
---

## Practical Example

Using ES6 features to simplify code:

**Example**:
```js
const openingHours = {
  thu: {
    open: 12,
    close: 22,
  },
  fri: {
    open: 11,
    close: 23,
  },
  sat: {
    open: 0, // Open 24 hours
    close: 24,
  },
};

const restaurant = {
  name: 'Classico Italiano',
  location: 'Via Angelo Tavanti 23, Firenze, Italy',
  categories: ['Italian', 'Pizzeria', 'Vegetarian', 'Organic'],
  starterMenu: ['Focaccia', 'Bruschetta', 'Garlic Bread', 'Caprese Salad'],
  mainMenu: ['Pizza', 'Pasta', 'Risotto'],

  // Using property shorthand for openingHours
  openingHours,

  // Method shorthand
  order(starterIndex, mainIndex) {
    return [this.starterMenu[starterIndex], this.mainMenu[mainIndex]];
  },
};

console.log(restaurant.order(1, 2)); // ['Bruschetta', 'Risotto']
```
---

## Key Points for Interviews

1. **Advantages of ES6 Enhancements**:
   - Property and method shorthand reduce boilerplate code.
   - Computed property names enable dynamic property creation.

2. **Common Use Cases**:
   - Creating structured data objects.
   - Encapsulating related functionality.

3. **Questions to Expect**:
   - How do ES6 features simplify object literal syntax?
   - What are computed property names, and how are they used?

#objects