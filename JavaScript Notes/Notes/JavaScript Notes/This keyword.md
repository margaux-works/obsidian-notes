# The JavaScript `this` keyword

The `this` keyword in JavaScript refers to the object it belongs to and is determined by the **execution context** (how a function is called). It allows:

- **Reusing functions** in different contexts.
- **Identifying the object** in the current execution context.

The value of `this` is resolved at **runtime** and depends on how the function is invoked.

```js
function showName() {
    console.log(this.name);
}
const name = "Alice";
showName(); // "Alice" (global context)

```

In strict mode:
```js
"use strict";
showName(); // TypeError: Cannot read properties of undefined
```

---

## **Implicit Binding**

When a function is called as a method of an object, `this` refers to the object.

### **Example**:
```js
function showAge() {
    console.log(this.age);
}
const user = {
    age: 30,
    showAge: showAge
};
user.showAge(); // 30

```

If nested objects are used, `this` refers to the object directly preceding the method call:

```js
const user = {
    age: 30,
    nested: {
        age: 40,
        showAge: showAge
    }
};
user.nested.showAge(); // 40

```

---
## **Explicit Binding**

You can explicitly set the `this` value using:

1. **`call()`**
2. **`apply()`**

### **Example**:
```js
function showAge() {
    console.log(this.age);
}
const user = { age: 25 };
showAge.call(user); // 25

```
### **Hard Binding**

Use `call()` inside another function to lock `this` to a specific object.
```js
function showAge() {
    console.log(this.age);
}
const user = { age: 35 };
const boundFunc = function() {
    showAge.call(user);
};
boundFunc(); // 35
boundFunc.call(window); // 35 (still bound to `user`)
```
---
## **Constructor Binding**

When a function is called with the `new` keyword:

1. A new object is created.
2. The new object is linked to the function's prototype.
3. `this` is set to the new object.

### **Example**:
```js
function User(age) {
    this.age = age;
}
const newUser = new User(40);
console.log(newUser.age); // 40
```
---
### **Summary**

- **Default Binding:** `this` is the global object (`window` or `global`).
- **Implicit Binding:** `this` is the object that calls the function.
- **Explicit Binding:** `this` is explicitly set with `call()` or `apply()`.
- **Constructor Binding:** `this` is the new object created with `new`.

