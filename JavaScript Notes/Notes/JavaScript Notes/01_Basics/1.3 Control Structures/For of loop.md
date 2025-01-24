# For...of Loop in JavaScript

The **for...of** loop, introduced in ES6, is a modern way to iterate over iterable objects such as arrays, strings, maps, sets, and more.

---

## Syntax

The `for...of` loop iterates over the values of an iterable object, rather than its indices (as in `for...in`).

**Basic Syntax**:
```js
for (const element of iterable) {
  // Code to execute for each element
}
```
---

## Examples

### Iterating Over an Array
The `for...of` loop makes iterating over arrays concise and readable:
```js
const menu = ['Pizza', 'Pasta', 'Risotto'];
for (const item of menu) {
  console.log(item);
}
// Output:
// Pizza
// Pasta
// Risotto
```

---

### Iterating Over a String
Strings are also iterable, and `for...of` loops through each character:
```js
const name = 'JavaScript';
for (const char of name) {
  console.log(char);
}
// Output:
// J
// a
// v
// a
// S
// c
// r
// i
// p
// t
```

---

### Iterating Over Maps
The `for...of` loop is especially useful with Maps, allowing iteration over both keys and values:
```js
const restaurant = new Map([
  ['name', 'La Piazza'],
  ['location', 'Rome'],
  ['categories', ['Italian', 'Vegetarian', 'Organic']],
]);

for (const [key, value] of restaurant) {
  console.log(`${key}: ${value}`);
}
// Output:
// name: La Piazza
// location: Rome
// categories: Italian,Vegetarian,Organic
```

---

### Iterating Over Sets
Sets are also iterable, and the `for...of` loop can iterate over unique values:
```js
const uniqueItems = new Set(['Pizza', 'Pasta', 'Pizza']);
for (const item of uniqueItems) {
  console.log(item);
}
// Output:
// Pizza
// Pasta
```

---

## Key Advantages

1. **Readable Syntax**:
   - Simpler and cleaner compared to `for` or `forEach`.

2. **Works with Any Iterable**:
   - Arrays, strings, maps, sets, DOM NodeLists, etc.

3. **Access to Values Directly**:
   - Eliminates the need to access values via indices.

---

## Important Notes for Interviews

1. **Difference Between `for...of` and `for...in`**:
   - `for...of` iterates over values of an iterable.
   - `for...in` iterates over the property keys of an object.

2. **Use Cases**:
   - Use `for...of` for arrays, strings, maps, or sets.
   - Avoid using it for objects; use `Object.keys`, `Object.values`, or `Object.entries` instead.

3. **Limitations**:
   - Cannot iterate over non-iterable objects like plain objects directly.
   - Use `Object.entries()` to iterate over object properties if needed.
