
```js
// spread operator 
const arr = [7, 8, 9];
const newArr = [1, 2, ...arr]; // if we wanted to add '1, 2' into the arr
console.log(newArr);
```

- useful to expend an array
- or to pass arguments into function

```js
// to add Gnocci to the existing values in the mainMenu
const newMenu = [...restaurant.mainMenu, 'Gnocci']; // creates a new array 
console.log(newMenu);
```

- is a bit similar to destructuring, but takes the entire array and creates a new array

### copy array
```js
const mainMenuCopy = [...restaurant.mainMenu];
console.log(mainMenuCopy);
```
### joins 2 arrays together
```js
const menu2 = [...restaurant.mainMenu, ...restaurant.starterMenu];
console.log(menu2);
```
### iterables: arrays, strings, maps, sets. NOT objects
```js
const str = 'Margo';
const letters = [...str, '', 'M.'];
console.log(letters);
console.log(...str); // expends string in individual elements
```

