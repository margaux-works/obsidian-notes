
## **BUILD FUNCTIONS**

- Functions can do anything
- group together set of instructions, often taking in values, doing some work and then returning a new value or set of values.
- Functions are created or defined and then they later can be call.

Example: 

```js
// create or defined a function
function calculateBill() {
  const total = 100 * 1.13; // bill * tax
  return total;
}

// call a function
calculateBill();
```

the total is not available out of the function, because we need to capture the return value of the function into a variable:

```js
const myTotal = calculateBill();
```

## **PARAMETERS AND ARGUMENTS**

![[Pasted image 20250115210529.png]]

function using parameters and arguments

```js
function calculateBill(billAmount, taxRate) {
  const total = billAmount * (1 + taxRate);
  return total;
}

const myTotal = calculateBill(500, 0.3);
```

you can pass expressions to a function

```js
const myTotal = calculateBill(20 + 20 + 30 + 20, 0.3);
```

and also you can pass functions as arguments

```js
function doctorize(firstName) {
  return `Dr. ${name}`;
}

function yell(name) {
  return `Hey ${name.toUpperCase()}`;
}

yell(doctorize("Cesar"));
// return "Hey DR. CESAR"
```

you can set default values to the parameters:

> taxRate = 0.13  
> tipRate = 0.15

if no one pass the parameter taxRate and tipRate for calculateBill function it will take by default the 0.13 for tax rate and 0.15 for tip rate

```js
function calculateBill(billAmount, taxRate = 0.13, tipRate = 0.15) {
  const total = billAmount + billAmount * taxRate + billAmount * tipRate;
  return total;
}

calculateBill(100);
```

if you want to use only one of the default values, like tipRate but not taxRate

```js
calculateBill(100, undefined, 0.2);
```

the undefined will fallback to the default value of 0.13 for taxRate

  

## **DIFFERENT WAYS TO DECLARE FUNCTIONS**

Javascript functions are values in themselves that can be stored into variables or can be passed into other functions.

there are different ways to declare functions

- ### Regular function declaration
    
    ```js
    function doctorize(firstName){
      return `Dr. ${fistName};
    }
    ```
    

- ### Anonymous function
    
    is a function without name
    
    ```js
    function (firstName){
      return `Dr. ${fistName};
    }
    ```
    

- ### Function Expression
    
    is an anonymous function stored into a variable
    
    ```js
    const doctorize = function (firstName){
      return `Dr. ${fistName};
    }
    ```
    
    the difference between regular function declaration and function expression is how they operate on the hoisting
    

- ### Arrow Function
    
    are anon functions, always need to be sticky into a variable.
    
    ```js
    //regular function:
    function inchToCM(inches) {
      const cm = inches * 2.54;
      return cm;
    }
    
    //arrow function:
    const inchesToCm = (inches) => inches * 2.54;
    ```
    
    other example:
    
    ```js
    //regular function:
    function add(a, b = 3) {
      const total = a + b;
      return total;
    }
    
    //arrow function
    const add = (a, b = 3) => a + b;
    ```
    
    you cannot delete the _()_ on _(a, b=3)_ because there are more than one parameter.
    

- ### Returning an Object
    
    ```js
    //regular function:
    function makeABaby(fisrName, lastName) {
      const baby = {
        name: `${first} ${last}`,
        age: 0,
      };
      return baby;
    }
    
    //arrow function:
    const makeABaby = (first, last) => {
      return (baby = {
        name: `${first} ${last}`,
        age: 0,
      });
    };
    
    //arrow function 2:
    const makeABaby = (first, last) => ({ name: `${first} ${last}`, age: 0 });
    ```
    

- ### IIFE
    
    means Immediately Invoked Function Expression
    
    ```js
    //anon function
    function(){
      console.log('Running the anon function');
      return 'you are cool';
    }
    
    //you can run immediately by doing this:
    (function(age){
      console.log('Running the anon function');
      return `you are cool and age ${age}`;
    })(10);
    ```
    

-