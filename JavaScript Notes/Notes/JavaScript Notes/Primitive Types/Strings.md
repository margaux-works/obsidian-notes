

represent letter, paragraphs, phases, etc. must be wrapped with quotes, double-quotes or back ticks, but needs to be consistent

```js
const name = "Wes";
const middle = "topher";
const last = `Bos`;
```

**sentence**  
with "\ esc", quotes, single quotes and backtick option:  
sentence = She´s so "cool"

```js
const sentence = 'she´s so "cool"';
const sentence = 'she´s so "cool"';
const sentence = `She's so "cool"`;
```

**concatenation & interpolation**
concatenation = strings can be added together 
Interpolation: = when you put a variable inside a string
```js
const hello = `hello my name is ${variable_name} nice yo meet you. I'm ${30 + 5} years old`;
```

- strings are indexed
  CHICKEN
  0123456
```javascript
let animal = 'chicken';
animal[1]
'h'
```

### concat method

```js
const array1 = ['a', 'b', 'c'];
const array2 = ['d', 'e', 'f'];
const array3 = array1.concat(array2);

console.log(array3);
// Expected output: Array ["a", "b", "c", "d", "e", "f"]
```

### String methods

**built-in** actions we can perform w/ individual strings like searching within a string, replacing part of a string, changing casing of a string etc.


- .toUpperCase()
- .trim() -> removes spaces at the end
- .slice() -> extracts a section of a string and returns it as a new string
- .replace
- .repeat

**string methods with arguments**
```
let tvShow = 'catdog';
tvShow.indexOf('cat'); // 0
tvShow.indexOf('dog'); // 3
```

### String Template Literals

String that allow embedded expression which will be evaluated and turn into a resulting string. 
```
`I counted ${3 + 4} sheep`
```
**Backticks** must be used for tagged template literals. 


#primitivetypes