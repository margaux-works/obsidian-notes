Javascript is a single threaded language, that means that only one thing can only be run at a time. Some other languages are multi thread, that means that they can run multiple process at once

> Javascript can only ever run one thing at once
![callback queue](https://github.com/CsarGomez/beginnersJavascriptNotes/raw/master/img/callbackQueue.png)
![Mastering the Event Loop: How JavaScript Works Under the Hood | by Debashis  Kar Suvra | Medium](https://miro.medium.com/v2/resize:fit:1400/1*iHhUyO4DliDwa6x_cO5E3A.gif)

```js
console.log('Starting');
setTimeout(function () {
    console.log('Running');
      }, 2000);
 console.log('Ending');
      ```
he output expected should be:

- starting
- running
- ending

but doesn't work that way, the way that Javascript works is that it will parse the first line

- `console.log("starting");`, then parse the next line
- `setTimeout(function(){ console.log("running") },2000);`  
    (setTimeout function) so it will "pin" in that and come back in 2 seconds, then go ahead and runs the next line
- `console.log("ending");` then 2 seconds later come back to the callback function that's been queued up

so based on that the result is:

- starting
- ending
- running




### Callback hell

The **CALLBACK HELL** also named as christmas tree code. if you need to do one thing after another, you must nest the callbacks inside of each other because they all depend on the previous callback to being called before it can then go ahead and run.
  