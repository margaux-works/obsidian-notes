

-  another control flow statement that can replace multiple statement
- least useful & important syntax which comes occasionally
- useful when we when we want to compare one value 
- does a strict comparison (===)

```js
const day = 'monday';
  

switch (day) {
case 'monday': // day === 'monday'
console.log('Plan course structure');
console.log('Go to codinng meetup');
break;
case 'tuesday':
console.log('Plan course structure');
break;
case 'wednesday':
case 'thursday':
console.log('write code examples');
break;
case 'friday':
console.log('record videos');
break;
case 'saturday':
case 'sunday':
console.log('enjoy the weekend');
break;
default:
console.log('not a valid day!');
}
```

below is the equivalent with if and else statement
```js
const weekday = 'tuesday';
      if (weekday === 'monday') {
        console.log('Plan course structure');
        console.log('Go to codinng meetup');
      } else if (weekday === 'tuesday') {
        console.log('Plan course structure');
      } else if (weekday === 'wednesday' || weekday === 'thursday') {
        console.log('write code examples');
      } else if (weekday === 'friday') {
        console.log('record videos');
      } else if (weekday === 'saturday' || weekday === 'sunday') {
        console.log('enjoy the weekend');
      } else {
        console.log('not a valid day');
      }
```
