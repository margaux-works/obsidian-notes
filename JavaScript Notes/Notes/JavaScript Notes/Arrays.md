Arrays are used to hold a list of items where the order matters.  
Each item in an array is called an **element**, and its position is called an **index**.  
The total number of elements is called the **length**.  
Elements can be of any data type: string, number, boolean, object, or even other arrays (nested arrays).

### **Syntax**

```js 
`const names = ["Alice", "Bob", "Charlie"];`
```

---

### **Accessing Elements**

- Arrays in JavaScript are zero-based (indexing starts at 0).
- Use **bracket notation** to access elements:
```js
console.log(names[0]); // Alice (1st element) console.log(names[2]); // Charlie (3rd element)
```

- To find the **length** of an array:
```js
console.log(names.length); // 3
```

- To access the **last element**:
```js
console.log(names[names.length - 1]); // Charlie
```

---

### **Mutable vs. Immutable Methods**

- **Mutable** methods modify the original array (e.g., `push`, `pop`, `splice`).
- **Immutable** methods return a new array without altering the original (e.g., `map`, `filter`, `slice`).

#### **Examples:**

**Mutable Method:**

```js
let numbers = [1, 2, 3]; numbers.reverse(); console.log(numbers); // [3, 2, 1] (original array is modified)
```

**Immutable Method:**

```js
let numbers = [1, 2, 3]; let slicedNumbers = numbers.slice(0, 2); console.log(slicedNumbers); // [1, 2] console.log(numbers); // [1, 2, 3] (original remains unchanged)
```

---
### **Adding Items**

- **To the end:** Use `push` (mutable).
```js
let names = ["Alice", "Bob"]; names.push("Charlie"); console.log(names); // ["Alice", "Bob", "Charlie"]
```

- **To the start:** Use `unshift` (mutable).
```js
names.unshift("Zara"); console.log(names); // ["Zara", "Alice", "Bob", "Charlie"]
```

- **To the middle:** Use `slice` with the spread operator (immutable).
```js
let bikes = ["A", "B", "D"]; let updatedBikes = [...bikes.slice(0, 2), "C", ...bikes.slice(2)]; console.log(updatedBikes); // ["A", "B", "C", "D"]
```

---

### **Removing Items**

- **From the end:** Use `pop` (mutable).
```js
names.pop(); console.log(names); // ["Zara", "Alice", "Bob"]
```

- **From the start:** Use `shift` (mutable).
```js
names.shift(); console.log(names); // ["Alice", "Bob"]
```


- **From a specific position:** Use `splice` (mutable).
```js
names.splice(1, 1); // Removes 1 element at index 1 console.log(names); // ["Alice"]
```


---

### **Copying and Cloning**

- Use the **spread operator** for shallow copies:

```js
let namesCopy = [...names];
```

- Use `JSON.parse(JSON.stringify(array))` for deep cloning nested arrays.

---

### **Finding and Removing Items**

Use `findIndex` and `slice` to remove items by condition (immutable).

``` js 
let comments = [   
{ id: 1, text: "Great!" },  
{ id: 2, text: "Okay" }, ]; 
let idToRemove = 2;  
let updatedComments = [   
...comments.slice(0, comments.findIndex(c => c.id === idToRemove)),
   ...comments.slice(comments.findIndex(c => c.id === idToRemove) + 1)
];
console.log(updatedComments); // [{ id: 1, text: "Great!" }]
```

---
### **Instance Methods**

-  `.join(separator)` → Convert array to a string.
  
```js
let fruits = ["apple", "banana"]; console.log(fruits.join(", ")); // "apple, banana"
```

- `.indexOf(item)` → Find index of an item.
  
```js
console.log(fruits.indexOf("banana")); // 1
```

- `.includes(item)` → Check if an item exists.

```js
console.log(fruits.includes("banana")); // true
```

### **Callback Methods**

- `.find()` → Find the first matching item.

```js
let found = fruits.find(fruit => fruit.startsWith("a")); console.log(found); // "apple"`

- `.filter()` → Create a new array with items that match a condition.



```js
let filtered = fruits.filter(fruit => fruit.startsWith("b")); console.log(filtered); // ["banana"]
```

- `.map()` → Create a new array by applying a function to each item.

```js
let upperCaseFruits = fruits.map(fruit => fruit.toUpperCase()); console.log(upperCaseFruits); // ["APPLE", "BANANA"]
```

- `.reduce()` → Reduce an array to a single value.

```js
let total = [1, 2, 3].reduce((sum, num) => sum + num, 0); console.log(total); // 6
```

---

### **Sorting Arrays**

- For strings, `.sort()` works alphabetically.

```js
let names = ["Charlie", "Alice", "Bob"]; console.log(names.sort()); // ["Alice", "Bob", "Charlie"]
```

- For numbers, use a comparator function.

```js
let numbers = [4, 2, 10]; console.log(numbers.sort((a, b) => a - b)); // [2, 4, 10]`
```

---