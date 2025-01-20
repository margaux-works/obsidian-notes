
Hoisting allows you to access functions and variables before they have been created, there´s two things in javascript that are hoisted:

- ### functions declarations
    
```javascript
    sayHi();
    
    function sayHi() {
      console.log("Hey!");
    }
    
    // Output - "Hey!"   
 ```
The above happens because when we run the JavaScript file, JavaScript compiler will take all function declarations and move them to the top of the file available for use.

**Suggestion:** Always define functions before using them.

Note: Functions made using a variable are not hoisted.
```js
add(10, 20);

const add = function(a,b) { return a + b;

}  
//Output - Uncaught ReferenceError: Cannot access 'add' before initialization
```

   
- ### variable declarations  
    javascript hoist variable declarations, but will not hoisted actual setting value:
    
    ```js
   
    console.log(age);
    var age = 10;
    
     // output -  undefined
    

    console.log(age);
    let age = 10;
    
    // Output - Reference error if you use let (age is not defined)
    ```
    

  

##