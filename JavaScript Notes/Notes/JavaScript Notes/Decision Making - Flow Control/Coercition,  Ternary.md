

### **Coercion**

![coercion](https://github.com/CsarGomez/beginnersJavascriptNotes/raw/master/img/coercion.png)

Coercion is when we force a different type, like string, number or an object, etc, into a real boolean. As an example, if we have a variable called `name`and we assign a string value to that variable we can coercing into true or false using the bang operator.  

```js
	name = 'Margo';
	!name // false
	!! name // true
```

### Ternary 

- ternary operator provides a shorthand for `if-else` statements.
- used to quickly assign or run functionality based on something being true or false.  
- needs 3 things:
	- condition
	- what to do if it's true
	- what to do if it's false

```js
 // if else without ternary
const count = 2;
let word;
if (count === 1) {
word = 'item';
} else {
word = 'items';
}
console.log(sentence);
  
// ternary
// 1. condition
// 2. what to do if true
// 3. what to do if false
const count = 2;
const word = count === 1 ? 'item' : 'items'; // if count is strictly equal to 1 then return 'item' if not return 'items'
const sentence = `You have ${count} ${word} in your cart`;
console.log(sentence);
```
another solution to make it even shorter is to use a template literal directly in the sentence:
```js
const sentence = `You have ${count} item${count === 1 ? '' : 's'} in your cart`;
```

another example of ternary use:
```js
function showAdminBar() {
console.log('showingAdminBar');
}

const isAdmin = true;
isAdmin ? showAdminBar() : null;
```

### Conditional Abuse

another way to 'abuse' conditions, often used in React is this
```js
is aAdmin && showAdminBar()
```
this is identical to 
```js
const isAdmin = true;
isAdmin ? showAdminBar() : null;
```

