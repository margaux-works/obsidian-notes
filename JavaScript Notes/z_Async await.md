

```js
function wait(ms = 0) {
        return new Promise((resolve) => {
          setTimeout(resolve, ms);
        });
      }

      async function go() {
        console.log('Starting');
        await wait(2000);
        console.log('Ending');
      }

      go();
```

- important to mark the function as async to use await. otherwise will give an error 'await is only valid in async function'


