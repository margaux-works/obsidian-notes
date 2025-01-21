
- looks exactly like the spread operator '...'
- is to pack elements into an array
- on the left side of the assignment operator (=)


```js
// REST, because on LEFT side of =
const [a, b, ...others] = [1, 2, 3, 4, 4];
console.log(a, b, others);
```

- collect elements that are ununsed in the destructuring element
  
  ```js
  const [pizza, , risotto, ...otherFood] = [
...restaurant.mainMenu,
...restaurant.starterMenu,
];

console.log(pizza, risotto, otherFood);
  ```
  
- does not include any skipped elements,  must be the last in the destructured assignment 
