# **For Loop in JavaScript**

The `for` loop is a fundamental control structure in JavaScript that allows code to be executed repeatedly while a specified condition evaluates to `true`.

---

## **Why Use For Loops?**
- Adheres to the "Don't Repeat Yourself" principle.
- Useful for iterating over arrays, performing repetitive tasks, and much more.

---

## **Syntax**
```javascript
for (initialization; condition; increment/decrement) {
  // Code to execute
}
```
- **Initialization**: A variable is initialized before the loop starts (e.g., `let i = 0`).
- **Condition**: The loop runs while this condition is `true`.
- **Increment/Decrement**: Updates the variable after each iteration.

### Example: Basic Loop
```javascript
for (let i = 1; i <= 5; i++) {
  console.log(`Iteration ${i}`);
}
// Output:
// Iteration 1
// Iteration 2
// Iteration 3
// Iteration 4
// Iteration 5
```

---

## **Looping Over Arrays**
Since arrays are zero-indexed, `for` loops typically start at `0` and go up to `array.length - 1`.

### Example:
```javascript
const array = ["A", "B", "C", "D"];

for (let i = 0; i < array.length; i++) {
  console.log(array[i]);
}
// Output:
// A
// B
// C
// D
```

---

## **Using `continue` and `break`**

- **`continue`**: Skips the current iteration and moves to the next one.
- **`break`**: Exits the loop entirely.

### Example: Using `continue`
```javascript
const data = [1, "hello", true, 42];

for (let i = 0; i < data.length; i++) {
  if (typeof data[i] !== "number") continue; // Skip non-numbers
  console.log(data[i]);
}
// Output:
// 1
// 42
```

### Example: Using `break`
```javascript
for (let i = 0; i < data.length; i++) {
  if (typeof data[i] === "number") break; // Exit when a number is found
  console.log(data[i]);
}
```

---

## **Looping Backwards**
To iterate through an array in reverse:

### Example:
```javascript
const array = ["A", "B", "C", "D"];

for (let i = array.length - 1; i >= 0; i--) {
  console.log(array[i]);
}
// Output:
// D
// C
// B
// A
```

---

## **Nested Loops**
A loop inside another loop is called a nested loop. Useful for iterating over multi-dimensional structures.

### Example:
```javascript
for (let exercise = 1; exercise <= 2; exercise++) {
  console.log(`Exercise ${exercise}`);

  for (let rep = 1; rep <= 3; rep++) {
    console.log(`  Repetition ${rep}`);
  }
}
// Output:
// Exercise 1
//   Repetition 1
//   Repetition 2
//   Repetition 3
// Exercise 2
//   Repetition 1
//   Repetition 2
//   Repetition 3
```

---

## **ForEach vs For Loop**
`forEach` is a method specifically for arrays, often preferred for readability when working with arrays.

### Example:
```javascript
const toppings = ["Mushrooms", "Tomatoes", "Cheese"];

toppings.forEach((topping) => console.log(topping));
// Output:
// Mushrooms
// Tomatoes
// Cheese
```

### Differences:
| Feature        | `for` Loop        | `forEach`                |
|----------------|-------------------|--------------------------|
| Type           | General-purpose   | Array-specific           |
| Flexibility    | Works on anything | Only works on arrays     |
| Early Exit     | Supports `break`  | Cannot use `break`       |

---

## **Best Practices**
- Use meaningful variable names (`index` instead of `i` when appropriate).
- Avoid infinite loops by ensuring the condition will eventually become `false`.
- For arrays, consider `forEach` when `break` or `continue` is not needed.
