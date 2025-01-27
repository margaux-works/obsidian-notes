<a name="dom"></a>

Javascript can be run in many types of environment, can be run in the browser, in the server, in robots, the most popular is way to introduce is through the web browser.  

The browser turns your html into something that is called **DOM** (_Document Object Model_)

![DOM HTML tree](https://www.w3schools.com/js/pic_htmltree.gif)

- **The Window:**  
  is the global scope in the browser, _the window_ is everything about the current open window, including the browser bar, the tabs, scroll bars.

  ```js
  window.location;
  window.innerWidth;
  ```

- **The Document:**  
  Is responsible for everything from the opening `<html>` to the closing `</html>` including the `<!DOCTYPE html>`

- **The Navigator:**  
  Is in a higher level than the window.
  it gives you information about the device itself, like battery, webcam, audio access, gps coordinates, etc.

## **SELECTING ELEMENTS**

When you need to be able to access the specific elements on the page, like H2 tag (`<h2>`), a div tag (`<div>`), a button (`<button>`) or an image (`<img>`) you need to select them first, and then you can add content, change content, listen for clicks, you can do anything you want with it.

There are two main ways to select elements _QuerySelector_ and _QuerySelectorAll_ both take one argument and that is the CSS selector.

- ### QuerySelector

  gives you the first matching element

  ```js
  const p = document.QuerySelect("p");
  ```

  QuerySelector will return the first `<p>` element on the page

- ### QuerySelectorAll

  gives you a multiple elements

  ```js
  const p = document.QuerySelectAll("p");
  ```

  QuerySelectorALL will return all the `<p>` elements on the page

According to the following HTML we can grab divs, classes, or do parent-child selectors (like select an images that lives inside a class)

```html
<div class="items">
  <div class="item item1">
    <img src="http://img1.com" />
  </div>

  <div class="item">
    <img src="http://img2.link" />
  </div>
</div>
```

selecting a div with class of item:

```js
const item = document.QuerySelector(".item");
```

Look inside of an element that you already have selected (you can use QuerySelector on any other element):

```js
const item1 = document.QuerySelector(".item1");

const item1Image = item1.QuerySelector("img");
```

Looking for all the images that lives inside an element with class of item (parent-child select)

```js
const imgs = document.querySelectorAll(".item img");
```

Or we can select a div with the class of item

```js
const divItem = document.QuerySelector("div.item");
```

We can also have old to select elements from the DOM like:

- getElementById
- getElementsByClassName
- getElementsByTagName

<br>
## ELEMENT PROPERTIES AND METHODS

```html
<h2>I am a header</h2>
```

If we grab whatever element on the page like an `<h2>` we can see that this element is actually an object that has a lot of properties and methods, and we can see the properties by using `console.dir`

```js
const heading = document.QuerySelect("h2");
console.dir(heading);
```

one of these properties is _textContent_ and we can use them as _setters_ or _getters_

- **getter:** is when you get the actual content of the element

  ```js
  console.log(heading.textContent);

  // the output is:  i am a header
  ```

- **setter:** will update the content

      ```js
      heading.textContent = 'I am a new and updated header';
      ```

  Similar to _textContent_ we have _innerText_ and some of the differences between both are that _textContent_ returns every element in the node, _innerText_ only shows human-readable elements, and also doest return hidden elements meaning that is aware of CSS styling:

let's pretend we have this HTML:

```html
<h2>
  I am a heading.
  <style>
    h2 {
      color: red;
    }
  </style>
</h2>
```

so the different outputs from using textContent or innerText:

- textContent:

  ```js
    const heading = document.querySelector('h2');
    console.log(heading.textContent);

    // the output should be:
    I am a heading.
    h2 {
        color: red;
      }
  ```

- innerText:

  ```js
    const heading = document.querySelector('h2');
    console.log(heading.innerText);

    // the output should be:
    I am a heading
  ```

We also have properties to work with like _insertAdjacentText_ it takes two arguments, the first one is the position, and second one is the element:

- position:
  - beforebegin: before the element itself
  - afterbegin: inside the element, before its first child
  - beforeend: inside the element, after its first chld
  - afterend: after the element itself

Example:
we have the following HTML:

```html
<p class="pizza">this is how many pizzas i ate! 🍕</p>
```

and we want to put another pizza emoji at the end

```js
const pizzaList = document.QuerySelector('.pizza');

pizzaList.insertAdjacentText('beforeend', 🍕)
```

the result will be:

```html
<p class="pizza">this is how many pizzas i ate! 🍕 🍕</p>
```

Differences between nodes and elements:

```html
<p class="pizza">
  -----------------------> element and node this is how many pizzas i ate! 🍕
  -------> node 🍕 --------------------------------------> node
</p>
------------------------------------> element and node
```

- Elements: are inside a tag  
  [Element methods and properties](https://developer.mozilla.org/en-US/docs/Web/API/Element)
- Nodes: can be anything  
  [Nodes methods and properties](https://developer.mozilla.org/en-US/docs/Web/API/Node)

<br>

<a name="workingWithClasses"></a>

## **WORKING WITH CLASSES**

When you select an element there is a classList attributes on that, there are some methods for getting all of the classes as well as removing and adding multiple classes.

suppose we have the following HTML:

```html
<img class="nice" src="https://picsum.photos/600" />
```

now we have to select it:

```js
const pic = document.querySelector(".nice");

console.log(pic.classList);
```

If you look the output you will see the _prototype_ with the methods that you're able to call, like:

- add
- contains
- remove
- toggle

Example:  
let's add some CSS to the image tag, and do some animation to that image

```css
img {
  transition: all 0.2s;
}
.round {
  border-radius: 50%;
}
```

Now we will add the class of toggle to the image

```js
const pic = document.querySelector(".nice");

function toggleRound() {
  pic.classList.toggle("round");
}

// we are not learning about Event Listeners, it will be in the next module, this is just for the animation to work when user click it

pic.addEventListener("click", toggleRound);
```

> You can find the example [here](https://codepen.io/cgope/pen/eYzLEOw?editors=0110)

<br>

<a name="BuildInAndCustomDataAttributes"></a>

## **BUILD IN AND CUSTOM DATA ATTRIBUTES**

Attributes are anything provided to an element as an additional information, like classes, source, alternative, etc..

we will add the alternative (`alt`) attribute to the following image using javascript

```html
<img class="nice" src="https://picsum.photos/600" />
```

```js
const pic = document.querySelector(".nice");

pic.alt = "Cute"; // setter
console.log(pic.alt); // getter
```

Some of the attributes are only _getters_ like `naturalWidth` , other can be _getters_ and _setters_

The other way to get or set the attributes is by using `getAttribute()` or `getAttribute()`

```js
pic.setAttribute("alt", "Really cute"); // setter

console.log(pic.getAttribute("alt")); // getter
```

The difference between these methods is that `setAttribute` and `getAttribute` is that this method will also work for non-standard attributes.

For non-standard or custom attributes you have to use what are called _data attributes_

```html
<img class="custom" data-name="name" src="https://picsum.photos/600" />

<img data-description="description" src="https://picsum.photos/600" />
```

You can access into _data-attributes_ by using `dataset`:

```js
const custom = document.querySelector(.custom);

console.log(custom.dataset)
```

`dataset` will gives you an object with all the properties values that you have.

<br>

<a name="CreatingHTML"></a>

## **CREATING HTML**

The man way to create HTML in javascript is `document.createElement` but this only create the element (in memory) and don't put it on the page.  
Also you can't add classes or attributes, you have to do it in the way we learn before with `textContent`.
To put the elements into the DOM, we can add it to the page with API called `appendChild`.

**Example:** Create elements (`p`, `img`, and a `div`), add classes and attributes and add it to the page:

```js
//create a paragraph
const myParagraph = document.createElement("p");
myParagraph.textContent = "I am a p";
myParagraph.classList.add("special");

//create an image
const myImage = document.createElement("img");
myImage.src = "https://picsum.photos/500";
myImage.alt = "Nice photo";

//create a div
const myDiv = document.createElement("div");
myDiv.classList.add("wrapper");

//add it to the page
myDiv.appendChild(myImage);
myDiv.appendChild(myParagraph);
document.body.appendChild(myDiv);
```

> **Note:** is not necessary to use querySelector to grab the body, this is because the document gives us a reference to the body, this works for the popular elements

Every time you use `appendChild` what you're doing is modifying the DOM, and that causes the reflow, meaning that the browser have to repaint what is on the actual page.

There's another API to add elements to the page called `insertAdjacentElement`, that can takes 4 different positions:

- beforebegin: before the targetElement itself
- afterbegin: inside the targetElement, before its first child
- beforeend: inside the targetElement, after its first chld
- afterend: after the targetElement itself

Lets add a header to the example before:

```js
const heading = document.createElement("h2");
heading.textContent = "Cool things";

myDiv.insertAdjacentElement("afterbegin", heading);
```

<br>

<a name="HTMLFromStringsAndXSS"></a>

## **HTML FROM STRINGS AND XSS**

This is a different approach using back ticks strings that we learn earlier, there is a potential security hole related to XSS (Cross-site scripting), that we learn how to prevent on the Security Section of this course.

Similar to `innerText` awe can use **`innerHTML`** as a setter, using strings instead of regular document.createElement, with `innerHTML` you can create tags, also we can interpolate values easily, and if its a valid HTML the browser will take it and parse it into all the items:

Example:  
we have the following HTML and we want to add an image with source and description, that will be inside a `div` with a class or wrapper:

```HTML
<article class="item">

</article>
```

In javascript:

```js
const item = document.querySelector(".item");

const src = `https://picsum.photos/200`;
const desc = `cute pup`;

const myHTML = `
<div class="wrapper">
  <h2>${desc}</h2>
  <img src="${src}" alt="${desc}"/>
</div>
`;
```

But these are not elements, are strings, you can check by using
`typeof myHTML`, meaning that we can't add classes, it only becomes an element by dump it into the DOM by setting the `innerHTML` like:

```js
item.innerHTML = myHTML;
```

Now you can add classes or whatever you want.

There is a ways you can do the same without `innerHTML` is:

- `document.createRange().createContextualFragments()`

using this, the HTML will not be visible in the page, but you will be able to select it using javascript.  
So lets turn **myHTML** from the example before into a DOM element using `document.createRange()`

```js
const myFragment = document.createRange().createContextualFragment(myHTML);
```

now we can add the fragment into the page by using `append`, `appendChild` or `insertAdjacent`:

```js
document.body.appendChild(myFragment);
```

<br>

<a name="TraversingAndRemovingNodes"></a>

## **TRAVERSING AND REMOVING NODES**

We have some properties available for us to work with elements, like:

- `el.children`
- `el.firstElementChild`
- `el.lastElementChild`
- `el.previousElementSibling`
- `el.nextElementSibling`
- `el.parentElement`

We also have these properties for nodes:

- `el.childNodes`
- `el.firstChild`
- `el.lastChild`
- `el.previousSibling`
- `el.nextSibling`
- `el.parentNode`

> **Note:** the word `el` means Element

you can remove by using `remove()`, for example: lets create a paragraph, turn into and element, added to the page and then remove it.

```js
const p = document.createElement("p");
p.textContent = "i will be removed";
document.body.appendChild(p);

p.remove();
```

this will remove the paragraph from the page, but still able in memory, so you can simply added again by using `appendChild` or other way to add the element into the page.

