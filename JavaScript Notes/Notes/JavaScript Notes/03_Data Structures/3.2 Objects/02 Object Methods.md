
## Functions inside Object

function can be inside objects
```js
 const margaux = {
        firstName: 'Margaux',
        lastName: 'Espinasse',
        birthYear: 1988,
        cat: ['Dolce', 'Reinette', 'Tintin'],
        job: 'developer',
        hasDriversLicense: false,

        calcAge: function (birthYear) {
          return 2024 - birthYear;
        },
      };
  console.log(margaux.calcAge(1988));
  ```

instead of repeating the age "1988" we can use `this`
```js
calcAge: function () {
          return 2024 - this.birthYear;
        },
      };
```

can be even simplifier like this:
```js
 const margaux = {
        firstName: 'Margaux',
        lastName: 'Espinasse',
        birthYear: 1988,
        cat: ['Dolce', 'Reinette', 'Tintin'],
        job: 'developer',
        hasDriversLicense: false,
        calcAge: function () {
          this.age = 2024 - this.birthYear;
          return this.age;
        },
      };
      
      console.log(margaux.calcAge());
console.log(margaux.age);
```

## Using Object.create() to create new Objects

The __Object.create()__ methods creates a new object, using an existing object as prototype of the newly created object. <br>

It contains __two__ parameter:
* First parameter is mandatory that serves prototype of new object to be created.
* Second is optional, it contains properties to be added to new object. <br>

E.g.

```JavaScript
const orgObject = { company: 'ABC' };
const employee = Object.create(orgObject, { name: { value: 'EmpOne'}});
console.log(employee); // {name: 'EmpOne'}
console.log(employee.name); // EmpOne
```

## Using Object.assign() to create new object

The __Object.assign()__ method is used to copy all enumerable own properties value from one or more source objects to target object. It will return target object. <br>


E.g.

```JavaScript
const orgObject = { company: 'ABC' };
const carObject = { carName: 'Corola' };
const employee = Object.assign({}, orgObject, carObject);

// Now you can get employee object that has company and carName as its property.

console.log(employee); // {company: 'ABC', carName: 'Corola'}
```

## Using Object.defineProperties()

This method defines __new__ or __modify__ existing property on object.

```JavaScript
const object1 = {};
Object.defineProperties (object1, {
    property1: {
        value: 42
    }
});
console.log(object1.property1); // 42
```
Similarly, we also have __Object.defineProperty()__

## Using Object.Entries()

It returns an array of object's __key value__ pairs. <br>
The order of array is same as provided by a __for__ in loop

```JavaScript
const object1 = {
    a: 'something', 
    b: 'nothing'
};
for (const [key, value] of Object.entries(object1)) {
    console.log(`${key}: ${value}`);
}
/* Output:
    a: something
    b: nothing
*/
```
