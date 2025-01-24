things on the [[The DOM]] can emit events, when they're clicked, hovered, dragged, etc.

We can use event listener to listen for when these events happen and do something, react to them.
You can attach event listeners to all elements, also the window and the document.

As an example, lets attach an event listener to a bottom.

```html
<body>
  <button class="butts">Click Me!</button>
</body>
```


```js
// select elements
const butts = document.querySelector(".butts");

// add the event listener
butts.addEventListener("click", function () {
  console.log("it got clicked!");
});
```

`addEventListener` will take usually two arguments, the first one is the type of event that you want to listen to (click, hover, mouseEnter, drag) ), and the second one is a callback function

> **NOTE:** callback function is a regular [[01 Functions]] that will be called in a later point and the browser will call that function for us when it needs to.

#dom #events 