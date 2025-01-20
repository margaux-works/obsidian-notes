# **Array Methods: Reduce, Filter, and Find**

![map(), filter() and reduce() in JavaScript | by Nikhil K Mannem | codeburst](https://miro.medium.com/v2/resize:fit:880/0*cQwPe6QPdl_-ByOq.png)
## **Reduce Method**

The `reduce()` method applies a function to each element of an array, reducing it to a single value. It’s useful for aggregating data, such as summing numbers or building objects.

### **Syntax**
```javascript
array.reduce(callback, initialValue);
```
- **`callback`**: A function executed on each element of the array. It receives:
  1. **`accumulator`**: The accumulated value returned by the previous callback.
  2. **`currentValue`**: The current element being processed.
  3. **`currentIndex`**: (Optional) The index of the current element.
  4. **`array`**: (Optional) The array `reduce()` was called on.
- **`initialValue`**: (Optional) The initial value for the accumulator.

### **Example: Sum Numbers**
```javascript
const numbers = [10, 20, 30];
const total = numbers.reduce((sum, num) => sum + num, 0);
console.log(total); // 60
```

### **Advanced Example: Inventory Management**
```javascript
const inventory = [
  { type: 'shirt', price: 4000 },
  { type: 'pants', price: 4532 },
  { type: 'socks', price: 243 },
  { type: 'pants', price: 2343 },
];

// Count each item type
const itemCounts = inventory.reduce((acc, item) => {
  acc[item.type] = (acc[item.type] || 0) + 1;
  return acc;
}, {});
console.log(itemCounts); // { shirt: 1, pants: 2, socks: 1 }

// Calculate total inventory value
const totalValue = inventory.reduce((total, item) => total + item.price, 0);
console.log(totalValue); // 11118
```

---

## **Filter Method**

The `filter()` method creates a new array containing elements that pass a given test (return `true` in the callback).

### **Syntax**
```javascript
array.filter(callback);
```
- **`callback`**: A function executed on each element. It receives:
  1. **`currentValue`**: The current element being processed.
  2. **`currentIndex`**: (Optional) The index of the current element.
  3. **`array`**: (Optional) The array `filter()` was called on.

### **Example: Filter Ages**
```javascript
const users = [
  { name: 'Alice', age: 25 },
  { name: 'Bob', age: 15 },
  { name: 'Charlie', age: 35 }
];

const adults = users.filter(user => user.age >= 18);
console.log(adults); // [{ name: 'Alice', age: 25 }, { name: 'Charlie', age: 35 }]
```

### **Example: Filter by Condition**
```javascript
const numbers = [1, 2, 3, 4, 5, 6];
const evenNumbers = numbers.filter(num => num % 2 === 0);
console.log(evenNumbers); // [2, 4, 6]
```

---

## **Find Method**

The `find()` method returns the **first element** in the array that passes a given test. If no element passes, it returns `undefined`.

### **Syntax**
```javascript
array.find(callback);
```
- **`callback`**: A function executed on each element. It receives:
  1. **`currentValue`**: The current element being processed.
  2. **`currentIndex`**: (Optional) The index of the current element.
  3. **`array`**: (Optional) The array `find()` was called on.

### **Example: Find a User by Name**
```javascript
const users = [
  { id: 1, name: 'Alice' },
  { id: 2, name: 'Bob' },
  { id: 3, name: 'Charlie' }
];

const bob = users.find(user => user.name === 'Bob');
console.log(bob); // { id: 2, name: 'Bob' }
```

### **Comparison with `filter()`**
- **`filter()`** returns **all matching elements** as an array.
- **`find()`** returns **only the first match** as an element.

---

## **Comparison Table: Reduce, Filter, Find**

| Method   | Returns                       | Use Case                                 |
|----------|-------------------------------|------------------------------------------|
| `reduce` | A single value                | Aggregation (e.g., sum, total, object creation) |
| `filter` | A new array of matching items | Filtering elements based on a condition |
| `find`   | First matching element        | Finding a specific element              |

---

These methods are versatile and powerful for manipulating arrays. Let me know if you'd like to dive deeper into specific use cases!
