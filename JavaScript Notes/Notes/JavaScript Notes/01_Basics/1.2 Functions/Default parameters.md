# Default Parameters in JavaScript (Introduced in ES6)

Default parameters allow you to set initial values for function parameters if no value is provided or if `undefined` is passed. This simplifies handling default values in functions.

---

## Key Features

1. **Avoid `undefined` Values**:
   - If a parameter is not passed or explicitly set to `undefined`, the default value is used.
2. **Defined Directly in Function Signature**:
   - ES6 introduced the ability to define default values directly in the function signature, making code cleaner and more concise.

---

## Syntax and Example

**Defining Default Parameters**:
```js
const createBooking = function (
  flightNum,
  numPassengers = 1,
  price = 199 * numPassengers
) {
  const booking = { flightNum, numPassengers, price };
  console.log(booking);
};

createBooking('LH123'); // Default values used: { flightNum: 'LH123', numPassengers: 1, price: 199 }
createBooking('LH123', 2, 800); // Provided values override defaults
```
---

## ES5 Alternative

Before ES6, default values were manually set using logical operators:
```js
function createBookingES5(flightNum, numPassengers, price) {
  numPassengers = numPassengers || 1;
  price = price || 199;
  const booking = { flightNum, numPassengers, price };
  console.log(booking);
}
```
---
## Combining Default Parameters with Other Features

1. **Expressions as Default Values**:
   
   - Default parameters can be set using expressions, such as calculations or function calls.
```js
const calculatePrice = (numPassengers) => numPassengers * 199;

function createBookingWithExpression(flightNum, numPassengers = 1, price = calculatePrice(numPassengers)) {
  console.log({ flightNum, numPassengers, price });
}

createBookingWithExpression('LH456'); // { flightNum: 'LH456', numPassengers: 1, price: 199 }
createBookingWithExpression('LH456', 3); // { flightNum: 'LH456', numPassengers: 3, price: 597 }
```
2. **Interaction with `undefined`**:
   
   - Only `undefined` triggers the use of default parameters. Passing `null` will not.

```js
function testDefault(param = 'default') {
  console.log(param);
}

testDefault(undefined); // 'default'
testDefault(null); // null
```

--- 
## Key Points for Interviews 

1. **Advantages**: 
- Cleaner syntax compared to ES5 methods.
- Reduces manual checks for `undefined`. 

2. **Limitations**: 
- Default parameters are only applied when the value is `undefined`, not for other falsy values like `null` or `0`. 

3. **Practical Use Cases**: 
- Setting defaults for optional function arguments. 
- Avoiding side effects when no arguments are provided. 

4. **Tech Questions**: 
- How does JavaScript handle default parameters when `undefined` is explicitly passed? 
- Can you use function calls as default parameter values?
