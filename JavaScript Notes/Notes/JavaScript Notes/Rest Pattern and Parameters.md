
The **rest pattern** and **rest parameters** allow you to collect multiple elements into a single array or object. They are denoted by `...` (three dots) and are commonly used in functions, destructuring, and variable assignment.

---

## Key Concepts

1. **Rest Pattern**:
   - Used to "pack" remaining elements into an array or object.
   - Appears on the **left-hand side** of the assignment or parameter list. // compared to spread operators which appears on the right side 

2. **Difference from Spread Operator**:
   - **Rest**: Packs elements into a collection (array or object).
   - **Spread**: Spreads elements out into individual values.
   - Example:
     ```js
     const arr = [1, 2, 3, 4];
     const [a, b, ...rest] = arr; // Rest packs elements into 'rest'
     console.log(a, b, rest); // 1 2 [3, 4]
     ```

---

## Rest Pattern in Destructuring

### Array Destructuring
- Rest collects the unused elements into an array.
- Must be the **last element** in the destructuring assignment.

**Example**:
```js
const [a, b, ...others] = [1, 2, 3, 4, 5];
console.log(a, b, others); // 1 2 [3, 4, 5]
```

### Skipped Elements

- Rest pattern **does not include skipped elements** in destructuring.

**Example**:
```js
const [pizza, , risotto, ...otherFood] = [
  "Margherita",
  "Pasta",
  "Risotto",
  "Salad",
  "Soup",
];
console.log(pizza, risotto, otherFood); // "Margherita" "Risotto" ["Salad", "Soup"]
```
---

## Rest Parameters in Functions

- Used to handle a **variable number of arguments** in functions.
- Collects remaining arguments into an array.

**Example**:
```js
function add(...numbers) {
  return numbers.reduce((acc, curr) => acc + curr, 0);
}
console.log(add(2, 3, 4)); // 9
console.log(add(1, 2, 3, 4, 5)); // 15

```
---

## Common Interview Questions

1. **What is the difference between the rest pattern and the spread operator?**
    
    - Rest packs elements into an array or object.
    - Spread expands elements from an array or object into individual values.
    
2. **Can the rest pattern appear anywhere in a destructuring assignment?**
    
    - No, the rest pattern must be the **last element** in a destructuring assignment.
      
3. **How does the rest pattern handle skipped elements?**
    
    - It **excludes skipped elements** from the packed collection.