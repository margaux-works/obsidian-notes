 - **var** (_value can be updated_) - old variable keyword
- **let** (_value can be updated_) - introduced with ES6 in 2015
- **const** (_value can't be updated_) - introduced with ES6 in 2015

```js
var name = "Wes";
let age = 100;
const cool = true;
```

In strict mode, we have to define a variable first before assigning a value to it.

```javascript
dog = 'snickers'; // bad coding, don't do this

console.log(dog); // snickers (no error)

'use strict';  
dog = 'snickers'; // error: dog is not defined
```

If we write `var dog;` dog is undefined. 

- Scoping:
	- **var** : function scoped (only available inside parent functions)  
	- **let** and **const** : block scoped (available inside a block denoted by { } )

## Variable Scope in JavaScript

The variable may exist in a __block__, __inside function__ or __outside function__. <br>

A `block` is section of code inside { } <br>

```JavaScript
// It has Block Scope
{
    let name = 'John Kabir';
}
```
A function is a bunch of code you want to place logically together. <br>
It is declared using __function__ keyword.

```JavaScript
// It has Function Scope
function test() {
    let name = 'Tahsan';
}
```
Everything declared outside of block and function is __global Scope__.<br>

```JavaScript
// It has Global Scope
const skyColor = 'blue';

{
    console.log(skyColor); // blue
}

function printSkyColor() {
    console.log(skyColor); // blue
}
printSkyColor();
```

So, there are three types of Scope:
1. Block Scope
2. Function Scope
3. Global Scope

The three keyword __var__, __let__ and __const__ work around these scopes.
## Variable naming conventions

- Should not start with capital unless they are a class
- Must start with a-z or _ or $
- only non alphanumerical accepted are _ or $ _
- If a variable is multi-word, you can use:
	- Camel-case: let iLovePizza = true;  
	- Upper Camel case (in case of classes): ILovePizza 
	- Snake case: let i_love_pizza=true;


> Tips:
> - Use const by default; if the value of the variable needs to change then use let
> - Almost never use var .
