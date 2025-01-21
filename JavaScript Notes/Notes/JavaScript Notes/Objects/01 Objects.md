> part about destructuring objects at the end

- a data structure like arrays
- properties are key-value
- the order of the value does not matter when we want to retrieve them, whereas in array the order matters because we access them with the index. instead with objects we use custom keys. 
  
![JavaScript Most important Thing! Object - DEV Community](https://media2.dev.to/dynamic/image/width=800%2Cheight=%2Cfit=scale-down%2Cgravity=auto%2Cformat=auto/https%3A%2F%2Fdev-to-uploads.s3.amazonaws.com%2Fuploads%2Farticles%2Fvmjy1hoc7uz7glniywz9.png)
object literals syntax:
```js
const margaux = {
firstName: 'Margaux',
lastName: 'Espinasse',
age: 36,
cat: ['Dolce', 'Reinette', 'Tintin'],
'cool-boi': true,
'really cool': false,
777: true,
clothing: {
shirts: 20,
pants: 5
}
};
```
key can have space, dash or can be numbers, can also have nested objects

### **Adding/modify a property**

  Adding a property after the object has been created is possible, same syntax if you want to over-write a property:

  ```js
  // add new property
  person.job = "Web Developer";

  //over-write a property
  person.age = 50;
  ```


### Frozen Object###

  You can modify any property of the object, but if you want to create an object that can't be modified any of their properties you can use **frozen object**:

  ```js
  const personFroze = object.freeze(person);
  ```

`Objects.freeze(person)` and it will return a NEW object `person.Froze`

### How to retrieve info from an object
can be done with a dot or Bracket

```js
console.log(margaux.lastName);
console.log(margaux['lastName']);

const nameKey = 'Name';
console.log(margaux['first' + nameKey]);
console.log(margaux['last' + nameKey]);

```
when to use brackets:
- when we need to first compute the property name (like example above)
when to use dot:
- in any other case use the dot

another example when it is useful to use brackets
```js
const interestedIn = prompt( 'What do you want to know about Margaux? Choose between firstName, lastName, age and cat');
console.log(margaux[interestedIn]);
      ```


### **Delete Object properties**

  To delete a property of an object you can use the `delete` key word

  ```js
  delete person.job;
  ```


## **OBJECT REFERENCE VS VALUES**

- ### **Compare Objects**

  When we compare objects is important to know that the comparison is done by reference to the object and not the values inside of it.  
  meaning that we can have:

  ```js
  const person1 = {
    first: "Cesar",
    last: "Gomez",
  };

  const person2 = {
    first: "Cesar",
    last: "Gomez",
  };
  ```

  and if we compare `person1` vs `person2`, the result should be false

  ```js
  person1 === person2; // result is false
  ```

- ### Copy Objects

  Theres a couple ways you can make a copy of an object, one of them is using **spread** (3 dot operator) another way is with `Object.assign` but this is an old way

  ```js
  //spread
  const person3 = { ...person1 };

  //Object assign
  const person3 = Object.assign({}, person1);
  ```

  > with these ways to copy and object you can only go one level deep

  If you want to do a deeper copy or a deep clone of all of the properties (an object with another object inside) you may use a utility library called [lodash](https://lodash.com/).

  If you do

  ```js
  const person3 = person1;
  ```

  This will not do a copy, it just reference or point the person3 to the original person1, meaning that if you update something on one of those the other will be updated with same values as well


- ### **Merge Objects**

  The spread also can be helpful to merge 2 or more objects into 1

  ```js
  const meatInventory = {
    bacon: 2,
    sausage: 3,
  };

  const veggieInventory = {
    lettuce: 5,
    tomatoes: 3,
  };

  //merge
  const Inventory = { ...meatInventory, ...veggieInventory };

  //result
  const meatInventory = {
    bacon: 2,
    sausage: 3,
    lettuce: 5,
    tomatoes: 3,
  };
  ```

  If you have duplicated values, meaning that the objects that you want to merge contains the same properties but with different values, the merge will take the value of the object that you put at the end, in this case _veggieInventory_
  

  - If you passed an Object or Array into a function, you will modified:

```js
//function
function doStuff(data) {
  data.tomatoes = 10000000000;
}

//run the function with an object as an argument
doStuff(inventory);
```

This will modify the tomatoes property on inventory object to be:

```js
const meatInventory = {
  bacon: 2,
  sausage: 3,
  lettuce: 5,
  tomatoes: 10000000000,
};
```


### **Destructuring Objects**

Destructuring objects allows you to extract properties from an object and assign them to variables, making your code cleaner and easier to read. It is widely used in modern JavaScript applications.

---

#### **Basic Destructuring**
- Extract values from an object into variables:
  ```js 
  const { name, openingHours, categories } = restaurant;
   console.log(name, openingHours, categories);
```
---

#### **Renaming Variables**
- Assign object properties to variables with different names using `:`:
 ```js
 const { name: restaurantName, openingHours: hours, categories: tags } = restaurant;
 console.log(restaurantName, hours, tags);
```

---

#### **Setting Default Values**
- Provide default values to variables in case a property is `undefined`:
   ```js
   const { menu = [], starterMenu: starters = [] } = restaurant;
   console.log(menu, starters);
```

---

#### **Nested Destructuring**
- Extract nested object properties:
   ```js
   const {
    fri: { open: o, close: c },
   } = openingHours;
  console.log(o, c);
```

