# JavaScript Operators

JavaScript operators perform operations on values, enabling you to manipulate data efficiently. Here are key operators to know for both day-to-day coding and technical interviews.

---

## Arithmetic Operators

1. **Addition (`+`)**:
   - Adds two values or concatenates strings.
```js
const sum = 5 + 10; // 15
const greeting = 'Hello' + ' ' + 'World'; // Hello World
```

2. **Subtraction, Multiplication, Division (`-`, `*`, `/`)**:
   - Perform basic arithmetic operations.
```js 
const difference = 10 - 5; // 5
const product = 4 * 5; // 20
const quotient = 20 / 4; // 5
```

3. **Remainder (`%`)**:
   - Returns the remainder of a division.
```js
const remainder = 10 % 3; // 1
```

4. **Exponentiation (`**`)**:
   - Raises a number to a power.
```js 
const squared = 2 ** 3; // 8
```

---

## Assignment Operators

1. **Basic Assignment (`=`)**:
   - Assigns a value to a variable.
```js
let x = 10;
```

2. **Shorthand Operators (`+=`, `-=`, `*=`)**:
   - Perform arithmetic and update the variable in one step.
```js
let result = 'Hello';
result += ' World';
console.log(result); // Hello World
```

---

## Logical Operators

### **OR (`||`)**
- Returns the first truthy value or the last value if all are falsy.
```js
console.log(3 || 'Margo'); // 3
console.log(undefined || 0 || '' || 'Hello'); // Hello
```

**Short-Circuiting**:
- If the first value is truthy, the second value is ignored.

**Practical Use**:
```js
const numGuests = restaurant.numGuests || 10;
console.log(numGuests); // Defaults to 10 if numGuests is falsy
```

**OR Assignment**:
```js
rest1.numGuests ||= 10;
rest2.numGuests ||= 10;
```

---

### **AND (`&&`)**
- Returns the first falsy value or the last value if all are truthy.
```js
console.log(0 && 'Jonas'); // 0
console.log(7 && 'Jonas'); // Jonas
```

**Short-Circuiting**:
- If the first value is falsy, the second value is ignored.

**Practical Use**:
```js 
restaurant.orderPizza && restaurant.orderPizza('mushrooms', 'cheese');
```

**AND Assignment**:
```js
books[i].highlighted &&= books[i].thirdParty?.goodreads?.rating >= 4.2;
```

---

### **Nullish Coalescing (`??`)**
- Returns the right-hand operand if the left-hand operand is `null` or `undefined`.
```js
const numGuests = restaurant.numGuests ?? 10;
console.log(numGuests); // Defaults to 10 only if numGuests is null or undefined
```

**Nullish Assignment**:
```js 
rest1.numGuests ??= 10;
rest2.numGuests ??= 10;
```

**Comparison with OR**:
- Unlike `||`, `??` does not treat `0` or `''` as falsy.

---

## Comparison Operators

1. **Strict Equality (`===`)**:
   - Checks both value and type.
```js
console.log(5 === '5'); // false
```

2. **Loose Equality (`==`)**:
   - Performs type coercion before comparing.
```js
console.log(5 == '5'); // true
```

---

## Key Interview Topics

1. **Difference Between `||`, `&&`, and `??`**:
   - `||`: Returns the first truthy value.
   - `&&`: Returns the first falsy value.
   - `??`: Returns the right-hand value only if the left-hand value is nullish (`null` or `undefined`).

2. **Use Cases for Assignment Operators**:
   - Use `||=` for default values.
   - Use `&&=` to assign a value conditionally.
   - Use `??=` to handle nullish cases specifically.

3. **Short-Circuiting in Logical Operators**:
   - Logical operators short-circuit as soon as the result is determined, improving performance in conditional expressions.

---

This optimized note provides clear explanations, practical examples, and covers important topics for interviews. Let me know if you'd like further refinements!
