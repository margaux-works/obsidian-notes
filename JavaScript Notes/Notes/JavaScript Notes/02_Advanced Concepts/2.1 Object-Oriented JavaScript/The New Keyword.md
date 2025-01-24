# The `new` Keyword in JavaScript

The **`new`** keyword is used to create a new object instance based on a constructor function or class. It is essential for working with constructor functions, classes, and built-in JavaScript objects.

---

## How the `new` Keyword Works

When you use the `new` keyword on a function or class, it performs the following steps:
1. Creates a new, empty object.
2. Sets the `this` keyword in the constructor function or class to point to the new object.
3. Links the new object to the prototype of the constructor function or class.
4. Executes the constructor function or class with the provided arguments.
5. Returns the newly created object unless the constructor explicitly returns another object.

---

## Example: Using `new` with Built-in Constructors

The `new` keyword can be used with built-in objects like `Date`, `Array`, and `Object`.

**Example:**
```js
const myDate = new Date('August 11, 2025');

console.log(myDate); // Mon Aug 11 2025 00:00:00 GMT+0000 (UTC)
console.log(typeof myDate); // object
console.log(myDate instanceof Date); // true
```
---

## Using `new` with Custom Constructor Functions

You can define your own constructor functions to create objects using `new`.

**Example:**
```js
function Person(name, age) {
  this.name = name;
  this.age = age;
}

const john = new Person('John', 30);
console.log(john); // Person { name: 'John', age: 30 }
console.log(john instanceof Person); // true
```
---

## Using `new` with ES6 Classes

The `new` keyword is also used with ES6 classes to create instances.

**Example:**
```
class Car {
  constructor(make, model) {
    this.make = make;
    this.model = model;
  }
}

const myCar = new Car('Tesla', 'Model S');
console.log(myCar); // Car { make: 'Tesla', model: 'Model S' }
```
---

## Special Case: `new Set`

The `Set` object is a built-in data structure in JavaScript that stores **unique values**. Using `new Set` creates a Set instance, automatically removing duplicates.

**Example:**
```js
const keywords = ['javascript', 'html', 'javascript', 'css'];
const uniqueKeywords = [...new Set(keywords)];
console.log(uniqueKeywords); // ['javascript', 'html', 'css']
```
---

## Important Notes for Interviews

1. **When to Use `new`**:
   - Use `new` with constructor functions, classes, and built-in constructors like `Date`, `Set`, or `Map`.

2. **What Happens Without `new`**:
   - Calling a constructor function without `new` will cause `this` to refer to the global object (`window` in browsers) or `undefined` in strict mode.

3. **Difference Between `new` and Factory Functions**:
   - Factory functions return objects without using `new`. They are often preferred when you need more flexibility.

4. **Key Questions**:
   - What happens when you use `new` in JavaScript?
   - How is `new` different from using a factory function?
   - Can you explain the steps `new` performs internally?