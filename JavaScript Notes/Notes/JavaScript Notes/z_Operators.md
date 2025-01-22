

### How `+=` Works:

The `+=` operator is a shorthand for concatenation when building strings. It takes the existing value of the variable and appends the new value to it.

```js
let result = 'Hello';
result += ' World';
console.log(result); // Output: "Hello World"
```
### ||  - OR operator

can use any data type, return any type, short-circuiting
if first value is a truthy value it will return it immediately, JS will not even look at it (the next value)


Example
```js
console.log(3 || 'Margo'); // 3
console.log('' || 'Margo'); // 'Margo'
console.log(true || 0); // true
console.log(undefined || null); // null - happens even though null is also a falsy value
console.log(undefined || 0 || '' || 'Hello' || 23 || null); // 'Hello' - first truthy value
```

Example
```js
const guests1 = restaurant.numGuests ? restaurant.numGuests : 10;
console.log(guests1); // 10

const guests2 = restaurant.numGuests || 10; // easier method than using ternary statement
console.log(guests2); // 10 
```

Example 
```js
// OR assignment operator
// rest1.numGuests = rest1.numGuests || 10;
// rest2.numGuests = rest2.numGuests || 10;
rest1.numGuests ||= 10;
rest2.numGuests ||= 10;

console.log(rest1);
console.log(rest2);
```

### && - AND operator

Example 
```js
console.log(0 && 'Jonas'); // 0 - short-circuiting when first value if false and returns the first value without evaluating second operator
console.log(7 && 'Jonas'); // Jonas - when first value is truthy, the evaluation continues and return the last true operator
```

Example
```js
if (restaurant.orderPizza) {
  // if this function exists, then we execute it
  restaurant.orderPizza('mushrooms', 'eggs');
}

// same thing with AND statement
restaurant.orderPizza && restaurant, orderPizza('mushrooms', 'eggs');
```

### ?? - Nullish Operators

```js
const rest1 = {
  name: 'Capri',
  numGuests: 0,
};

const rest2 = {
  name: 'La Piazza',
  owner: 'Giovanni Rossi',
};
//nullish assignment (null or undefined)
rest1.numGuests ??= 10;
rest2.numGuests ??= 10;

console.log(rest1); // numGuest: 0
console.log(rest2); // numGuest: 10
```
if we would have use OR operator || numGuest for rest1 would have been 10 because 0 is falsy 