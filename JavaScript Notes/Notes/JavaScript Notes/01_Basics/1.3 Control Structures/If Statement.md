### Statements

- Statements are the foundation of all logic in javascript
- they expect boolean (either true or false.  )

### if statement###

- The `if` statement executes a block of code if a specified condition is true.

```js
if (10 > 2) {
  console.log("yes, 10 is greater than 2");
}
```

### else if ###
- The `else if` statement specifies a new condition if the previous condition is false.
"if. not the first thing is true, maybe this other thing?"

```js
if (10 > 2) {
  console.log("yes, 10 is greater than 2");
} else if (11 > 10) {
  console.log("yes, 11 is greater than 10");
} else if (3 > 1) {
  console.log("yes, 3 is greater than 1");
}
```

-  if the first one is true, even if the ones that come later are also true they will never run

If you want to check for multiple things that are true or false you will need three separate statements

```js
if (10 > 2) {
  console.log("yes, 10 is greater than 2");
}

if (11 > 10) {
  console.log("yes, 11 is greater than 10");
}

if (3 > 1) {
  console.log("yes, 3 is greater than 1");
}
```

The `else` statement executes a block of code if none of the previous conditions are true.
`else`-> "if nothing was true, do this" 

```js
const age = 50;

if (age > 70) {
  console.log("in your seventies");
} else if (age > 60) {
  console.log("in your sixties");
} else if (age > 50) {
  console.log("in your 50s");
} else {
  console.log("nothing was true");
}
```

### **Nested if-else Statement** 

`if-else` statements can be nested to check multiple conditions.

```js
let num = 10; 
if (num > 0) { 
	if (num % 2 === 0) {
	 console.log("Positive even number"); 
	} 
}
```



### If statements inside a function ###

And statement into a function can return different values, we have a function called slugify, and what this function does is take a sentence and a boolean of whether we should lowercase or not, then we return the sentence calling a replace method and using a _Regex_ (regular expression) we will replace the spaces for dashes.  

In this case Regex looks like this

```js
  /\s/g, "-";
 ```

Regex always start with an `/` and it closes with another slash `/`  
The `\s` is referring to and space  
The `g` is referring to a global, so find them all, not just the first space.  
Finally every space will be replaced by a dash.  
So this is the function:
```js

function slugify(sentence, lowercase) {
  if (lowercase) {
    return sentence.replace(/\s/g, "-").toLowerCase();
  } else {
    return sentence.replace(/\s/g, "-");
  }
}```

some developers prefers to keep as much logic out of the brackets, to prevent delete something, so lets remake the function
```js
function slugify(sentence, lowercase) {
  let slug = sentence.replace(/\s/g, "-");

  if (lowercase) {
    return slug.toLowerCase();
  }
  return slug;
}
```

The first thing is removing the else, since we are using the return is not necessary the else

> the return means to return a value from a function and stop that function from running.

Then we can create a variable for the replace.

Another way we can use statements in functions is for example if we have a function that checks if a name is inside a word like the word _awesome_
```js
function nameIsAwesome(name) {
 return "awesome".includes(name);
}
```

Then we can check with and if statement if that condition is true or false

```js
if (nameIsAwesome('wes')) {
console.log('Cool name');
}
```