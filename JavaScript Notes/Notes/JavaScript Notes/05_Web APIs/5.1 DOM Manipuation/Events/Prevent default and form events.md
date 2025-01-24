
There's a couple elements in HTML that have default functionality when they're clicked, for example a submit button, and we can stop the default action by using:

```js
event.preventDefault();
```

For example we want to prevent the submit default if the name of a input form is "chad"

```html
<div class="wrapper">
  <form name="singup">
    <label for="name">Name</label>
    <input type="text" id="name" name="name">
    <label for="email">Email</label>
    <input type="email" id="email" name="email">
    <input type="checkbox" id="agree" name="agree">
    <label for="agree"> I agree to the terms and conditions</label>
    <hr>
    <button type="submit">Submit</button>
  </form>
</div>
```

so our javascript should be something like:

```js
const signupForm = document.querySelector('[name="singup"]');

signupForm.addEventListener("submit", function (event) {
  const name = event.currentTarget.name.value;
  if (name.includes("chad")) {
    alert("sorry bro");
    event.preventDefault();
  }
});
```

The `preventDefault()` will help us to stop the default action, so if the name is chad it will not sent the information when you click submit, if you remove the `preventDefault()`, it will send the information after the validation.

> you can see the example [here](https://codepen.io/cgope/pen/eYdJWeb?editors=0010)

  

## **ACCESSIBILITY GOTCHAS AND KEYBOARD CODES**

The differences between buttons and links:  
Buttons are to be used for actions tha happen inside the application.  
Links are used to change the page.  
that means that links are not to be used where buttons are.

Every key has a code, and the event have a bunch of information theres a Wes Bos website called [keycode.info](https://www.keycode.info/) where you can literally just press on any key to get meta information about that key.