
- when you use the new keyword on a function it creates a new instance object of that function
## **THE NEW KEYWORD**

Using the NEW keyword in Javascript, will create a new object that is an instance of whatever function you have made it from

```js
  const myDate = new Date('August 11, 2025);

  console.log(myDate);
```

myDate is an instance of Date

```js
typeof myDate;
// object

myDate instanceof Date;
// true
```

functions: ![newKeyword](https://github.com/CsarGomez/beginnersJavascriptNotes/raw/master/img/newKeyword.png)


### new Set
```js
const uniqueKeywords = [...new Set(keywords)];
```
- A `Set` is a data structure in JavaScript that only stores **unique values**. It automatically removes duplicates when you pass an array to it.
- `new Set(keywords)` creates a Set from the `keywords` array, effectively removing duplicates.


