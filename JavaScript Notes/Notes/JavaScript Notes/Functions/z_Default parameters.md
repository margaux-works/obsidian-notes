
Default parameters in function can be defined.
when we don't pass an argument then it will be undefined, so we can define default value to avoid that 

```js
const bookings = [];

const createBooking = function (
  flightNum,
  numPassengers = 1,
  price = 199 * numPassengers
) {
  //   // ES5 way
  //   numPassengers = numPassengers || 1; // default value if undefined
  //   price = price || 199; // default value if undefined
  const booking = { flightNum, numPassengers, price };
  console.log(booking);
  bookings.push(booking);
};

createBooking('LH123');
createBooking('LH123', 2, 800);
```

ES6 addition allows us to define directly the default value in the parameters

