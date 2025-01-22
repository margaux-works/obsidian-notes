> to optmise all sections

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


### Split and Join

```js
const [firstName, lastName] = 'Jonas Schmedtmann'.split(' ');

const newName = ['Mr.', firstName, lastName.toUpperCase()].join(' ');
console.log(newName);

const capitalizeName = function (name) {
  const names = name.split(' ');
  const namesUpper = [];

  for (const n of names) {
    // namesUpper.push(n[0].toUpperCase() + n.slice(1));
    namesUpper.push(n.replace(n[0], n[0].toUpperCase()));
  }
  console.log(namesUpper.join(' '));
};

capitalizeName('jessica ann smith davis');
capitalizeName('jonas schmedtmann');

```


## Pad method

```js
const message = 'Go to gate 23!';
console.log(message.padStart(25, '+').padEnd(30, '+')); // Output: +++++++++++Go to gate 23!+++++
console.log('Jonas'.padStart(25, '+'));

const maskCreditCard = function (number) {
  const str = number + ''; // will convert the number in a string
  const last = str.slice(-4);
  return last.padStart(str.length, '*');
};

console.log(maskCreditCard(4365435331214)); // Output: *********1214
maskCreditCard('454654646783132131354');
```

### Repeat

```js
const message2 = 'Bad weather...All departures delayed...';
console.log(message2.repeat(5));

const planesInLine = function (n) {
  console.log(`There are ${n} planes in line ${'✈️'.repeat(n)}`);
};
planesInLine(5);
planesInLine(3);
planesInLine(12);
```


#primitivetypes