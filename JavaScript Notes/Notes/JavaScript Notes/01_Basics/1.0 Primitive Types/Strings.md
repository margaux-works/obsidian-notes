# Strings in JavaScript

Strings are one of the most commonly used data types in JavaScript, representing text. They are immutable and can be manipulated using a variety of methods and techniques.

---

## Creating Strings

Strings can be created using single quotes (`'`), double quotes (`"`), or backticks (`` ` ``). Use backticks for template literals when embedding expressions.

**Examples**:
```js
const name = "Wes";
const middle = 'Topher';
const last = `Bos`;

const sentence1 = "She's so \"cool\"";
const sentence2 = 'She\'s so "cool"';
const sentence3 = `She's so "cool"`;
```
---

## String Interpolation and Concatenation

1. **Concatenation**: Adding strings together using the `+` operator.
```js
const greeting = 'Hello, ' + 'world!';
console.log(greeting); // Output: Hello, world!
```
2. **Interpolation**: Embedding variables or expressions in strings using template literals.
```js 
const name = 'Margaux';
const age = 35;
console.log(`Hello, my name is ${name}. I am ${age} years old.`);
```
---

## String Indexing

Strings are zero-indexed, meaning each character is assigned a numeric index starting from 0.

**Example**:
```js
const word = 'CHICKEN';
console.log(word[0]); // Output: C
console.log(word[1]); // Output: H
```

---

## Common String Methods

1. **toUpperCase()**: Converts all characters to uppercase.
2. **toLowerCase()**: Converts all characters to lowercase.
3. **trim()**: Removes whitespace from both ends of a string.
4. **slice(start, end)**: Extracts a section of a string and returns it as a new string.
5. **replace(search, replacement)**: Replaces a specified value in a string.
6. **repeat(n)**: Repeats the string `n` times.

**Examples**:
```js
let phrase = '   Hello, World!   ';
console.log(phrase.trim()); // Output: Hello, World!

const food = 'hamburger';
console.log(food.slice(3, 7)); // Output: burg
```

---

## String Template Literals

Template literals allow embedded expressions, evaluated to produce a resulting string. Use backticks (`).

**Example**:
```js
const apples = 5;
console.log(`I have ${apples} apples.`); // Output: I have 5 apples.
```

---

## Split and Join

1. **split(separator)**: Splits a string into an array based on a separator.
2. **join(separator)**: Combines array elements into a string with a specified separator.

**Examples**:
```js
const [firstName, lastName] = 'Jonas Schmedtmann'.split(' ');
console.log(firstName, lastName); // Output: Jonas Schmedtmann

const newName = ['Mr.', firstName, lastName.toUpperCase()].join(' ');
console.log(newName); // Output: Mr. Jonas SCHMEDTMANN
```

---

## Padding Strings

1. **padStart(targetLength, padString)**: Pads the start of the string to a specified length.
2. **padEnd(targetLength, padString)**: Pads the end of the string to a specified length.

**Example**:
```js
const message = 'Gate 23';
console.log(message.padStart(10, '+').padEnd(15, '-')); // Output: ++++Gate 23-----
```

**Mask Credit Card**:
```js 
function maskCreditCard(number) {
  const str = String(number);
  const last4 = str.slice(-4);
  return last4.padStart(str.length, '*');
}

console.log(maskCreditCard(123456789012)); // Output: ********9012
```
---

## Repeating Strings

Use `.repeat(n)` to repeat a string `n` times.

**Example**:
```js
const warning = 'Bad weather... ';
console.log(warning.repeat(3)); // Output: Bad weather... Bad weather... Bad weather...

function planesInLine(n) {
  console.log(`There are ${n} planes in line ${'✈️'.repeat(n)}`);
}

planesInLine(5); // Output: There are 5 planes in line ✈️✈️✈️✈️✈️
```
