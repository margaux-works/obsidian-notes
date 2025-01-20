A `Callback functions` is function that is performed after another function has completed its execution. <br>
* It is typically supplied as an input to other function.
* __Callbacks__ are critical to understand, as they are used in array methods (such as __map()__, __filter()__, and so on), __setTimeout__, __eventlisteners__ (such as __click__, __scroll__). 

E.g.

```JavaScript
function orderPizza(type, name, callback) {
    console.log('Pizza ordered');
    console.log('Pizza is on preparation');

    setTimeout(function() {
        let msg = `Your ${type} ${name} Pizza is ready`;
        callback(msg);
    }, 3000);
}
```

Now Invocation of orderPizza:

```JavaScript
orderPizza('veg', 'cheese', function (message) {
    console.log(message);
});
```

__Important points to Note:__

* JavaScript function can accept other function as argument.
* passing function as argument is powerful programming concept that can be used to notify caller that something happened. <br> It is also known as __callback function__.
* Nesting too many callback function is not a great idea and it creates callback hell.

#functions 