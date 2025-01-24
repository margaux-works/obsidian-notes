# **`map()` Method**

The `Array.map()` method is used to create a **new array** by applying a **callback function** to each element of an existing array. It is a powerful tool for transforming data.

---

## **Key Features**
- The `map()` method **does not modify the original array**.
- It always returns a new array of the **same length** as the original.
- Works with **strings, numbers, objects**, and more.

---

## **Syntax**

```JavaScript
array.map(function(currentValue, index, array) {
    // return transformed value
}, thisArg);
```

### Parameters:
1. **`currentValue`**: The current element being processed.
2. **`index`**: (Optional) The index of the current element.
3. **`array`**: (Optional) The original array.
4. **`thisArg`**: (Optional) Value to use as `this` when executing the callback.

---

## **Basic Example**
```JavaScript
const numbers = [1, 2, 3, 4, 5];
const squared = numbers.map((num) => num * num);

console.log(squared); // [1, 4, 9, 16, 25]
```

---

## **Using `map()` with Arrays of Objects**
Transform or retrieve specific fields from objects in an array:

### Example 1: Combine Properties
```JavaScript
const users = [
    { firstName: 'John', lastName: 'Doe' },
    { firstName: 'Jane', lastName: 'Smith' }
];

const fullNames = users.map((user) => `${user.firstName} ${user.lastName}`);
console.log(fullNames); // ["John Doe", "Jane Smith"]
```

### Example 2: Calculate Age
```JavaScript
const people = [
    { name: 'Alice', birthday: '1990-01-01' },
    { name: 'Bob', birthday: '1985-05-15' }
];

const withAges = people.map((person) => {
    const age = new Date().getFullYear() - new Date(person.birthday).getFullYear(); // 2025 - 1990
    return { ...person, age }; // constructs new object by copying all existing properties and adds property age
});

console.log(withAges);
// [{ name: "Alice", birthday: "1990-01-01", age: 35 }, { name: "Bob", birthday: "1985-05-15", age: 40 }]
```

> The **`Date()`** constructor creates [`Date`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date) objects. When called as a function, it returns a string representing the current time.

- `.getFullYear()` retrieves the current year from that date.
```js
console.log(new Date().getFullYear()); // Output: (e.g., 2025)
```

---

## **Chaining with `map()`**
You can chain `map()` calls for multiple transformations.

### Example: Capitalize and Append a String
```JavaScript
const names = ['john', 'jane', 'jack'];

const formattedNames = names
    .map((name) => name[0].toUpperCase() + name.slice(1)) // extract all characters of the string 'name' starting from the second character (index 1)
    .map((name) => `${name} Doe`);

console.log(formattedNames); // ["John Doe", "Jane Doe", "Jack Doe"]
```

---

## **Adding a Context (`thisArg`)**
You can provide a custom context for the callback using `thisArg`.

### Example:
```JavaScript
const multiplier = {
    factor: 2, // This property will be accessed using 'this.factor'
    multiply(arr) {
        return arr.map(function (num) {
            return num * this.factor;
        }, this); // Pass the 'multiplier' object as 'thisArg'
    }
};

console.log(multiplier.multiply([1, 2, 3])); // [2, 4, 6]
```

**Callback Context in `map`:**

- Inside the callback function passed to `map()`, the `this` context would normally be `undefined` in strict mode or the global object (`window` or `global`) in non-strict mode.
- By passing `this` as the second argument, we ensure that the callback function uses the `this` from the `multiplier` object.
---

## **Comparison with Loops**
Using `map()` is often cleaner and more concise than traditional loops for transformations.

### Example: Multiply Elements
#### Using `for` Loop:
```JavaScript
let arr = [2, 3, 4];
for (let i = 0; i < arr.length; i++) {
    arr[i] = arr[i] * 3;
}
console.log(arr); // [6, 9, 12]
```

#### Using `map()`:
```JavaScript
const arr = [2, 3, 4];
const result = arr.map((el) => el * 3);
console.log(result); // [6, 9, 12]
```

---

## **Common Use Cases**
1. **Format Data**:
   ```JavaScript
   const numbers = [10.456, 20.123];
   const formatted = numbers.map((num) => num.toFixed(2));
   console.log(formatted); // ["10.46", "20.12"]
   ```
>  **toFixed()** method of Number values returns a string representing this number using fixed-point notation with the specified number of decimal places.

2. **Add Taxes**:
   ```JavaScript
   const prices = [100, 200, 300];
   const withTax = prices.map((price) => price * 1.15);
   console.log(withTax); // [115, 230, 345]
   ```

3. **Convert Data Types**:
   ```JavaScript
   const strNumbers = ["1", "2", "3"];
   const intNumbers = strNumbers.map(Number); // `Number` is a built-in  function that converts a value to a number.
   console.log(intNumbers); // [1, 2, 3]
   ```

---

## **Important Notes**
- **Performance**: Avoid using `map()` for side effects (e.g., `console.log`). Use `forEach` for such cases.
- **Always Return a Value**: If the callback doesn't return a value, the new array will contain `undefined`.
- **Immutable**: The original array remains unchanged.
