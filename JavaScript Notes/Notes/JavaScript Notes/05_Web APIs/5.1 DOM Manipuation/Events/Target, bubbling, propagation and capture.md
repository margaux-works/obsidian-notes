Continue with the last example "buy buttons"

```js
const buyButtons = document.querySelectorAll('button.buy');

function handleBuyButtonClick(){
  console.log('you are buying');
}

buyButtons.forEach(function(buyButton){
  buyButton.addEventListener('click, handleBuyButtonClick);
});
```

The `handleBuyButtonClick` function is handle the clicking for buttons, so how do i know which specific button they have clicked?
That information is hidden away in the **event object**
The event object is an is object that is filled with all kind of information of user useful information and methods to work with the event.

In order to access the event object, we modify our callback to accept a param that is the **event**

```js
function handleBuyButtonClick(event) {
  console.log("you are buying");
}
```

> **Note:** Parameters are placeholders so when we define a function we can put a parameter and call it event, and it doesn't matter how we called as long as is the first argument of our callback.<br> You can [click here](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener#The_event_listener_callback) for more information.

Now we can console log the event `console.log(event)` and we will see the pointer event, the pointer event is the consolidated of all the events we have like clicks, touches and all these mouse events.
We will use target and current target for the next examples.
Lets add a price to the buttons:

```HTML
<button data-price-"100" class="buy">Buy Item 1</button>
<button data-price-"200" class="buy">Buy Item 2</button>
<button data-price-"300" class="buy">Buy Item 3</button>
<button data-price-"400" class="buy">Buy Item 4</button>
<button data-price-"500" class="buy">Buy Item 5</button>
```

Now using the target we should be able to access the price of each button, but these price is a string so we will parse as number (float):

```js
const buyButtons = document.querySelectorAll("button.buy");

function handleBuyButtonClick(event) {
  console.log("you are buying");
  console.log(parseFloat(event.target.dataset.price));
}

buyButtons.forEach(function (buyButton) {
  buyButton.addEventListener("click", handleBuyButtonClick);
});
```

> You can find the example [here](https://codepen.io/cgope/pen/wvzMdaJ?editors=0010)

The difference between `target` and `currentTarget`?
The difference comes in when you have elements that are nested inside of the element that you are listening to, for example lets wrap the number of the buy button inside a strong tag

```HTML
<button data-price-"100" class="buy">Buy Item <strong>1</strong></button>
<button data-price-"200" class="buy">Buy Item <strong>2</strong></button>
<button data-price-"300" class="buy">Buy Item <strong>3</strong></button>
<button data-price-"400" class="buy">Buy Item <strong>4</strong></button>
<button data-price-"500" class="buy">Buy Item <strong>5</strong></button>
```

so if you click in the number inside the button you will notice that `event.target` is the thing that actually got clicked (the number) and the `event.currentTarget` is the thing that fired the event listener

Is possible to be clicking on multiple things at certain time, at that is **_propagation_** meaning that if we click in the strong tag, we also click the button, and we also click in the body, and also clicked the html, window, etc ...
The way that you can prevent that is with a method on the event that's called stop propagation

```js
// stop this event from bubbling up
event.stopPropagation();
```

The events can be the opposite, that is called **_Capture_** which is the opposite to propagation
the following image should explain this:
![[Pasted image 20250116092451.png]]


> you can click [here](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener) for more information about bubbling and capture
