
JavaScript provides two built-in methods, `setTimeout` and `setInterval`, to execute code after a delay or at repeated intervals.

---

## **setTimeout()**

The `setTimeout` method executes a function after a specified delay.

### **Syntax**
```javascript
setTimeout(callback, delay, ...args);
```
- **`callback`**: The function to execute.
- **`delay`**: The time in milliseconds to wait before executing the function.
- **`...args`**: Additional arguments to pass to the callback function.

### **Example**
```javascript
function buzzer() {
  console.log('BIIIIIP');
}

console.log('starting');
setTimeout(buzzer, 500); // Executes after 500ms
console.log('ending');
```

**Output:**
```
starting
ending
BIIIIIP
```
> **Note:** The output order is due to JavaScript's asynchronous nature.

### **Stopping a Timer**
To stop a timer created with `setTimeout`, use `clearTimeout()`.

### Example:
```javascript
function destroy() {
  document.body.innerHTML = `<p>DESTROYED</p>`;
}

const bombTimer = setTimeout(destroy, 5000);

window.addEventListener('click', function () {
  console.log('You clicked! You saved the world');
  clearTimeout(bombTimer); // Stops the timer
});
```

---

## **setInterval()**

The `setInterval` method repeatedly executes a function at a specified time interval.

### **Syntax**
```javascript
setInterval(callback, delay, ...args);
```
- **`callback`**: The function to execute repeatedly.
- **`delay`**: The interval in milliseconds.
- **`...args`**: Additional arguments to pass to the callback function.

### **Example**
```javascript
function buzzer() {
  console.log('BIIIIIP');
}

setInterval(buzzer, 2000); // Executes every 2 seconds
```

### **Starting an Interval Immediately**
The `setInterval` method waits for the first interval to elapse before running. To start immediately:

```javascript
function setImmediateInterval(funcToRun, ms) {
  funcToRun(); // Execute immediately
  return setInterval(funcToRun, ms); // Schedule regular intervals
}

setImmediateInterval(buzzer, 2000);
```

### **Stopping an Interval**
To stop a running interval, use `clearInterval()`.

#### Example:
```javascript
const poopInterval = setInterval(function () {
  console.log('💩');
}, 100);

setTimeout(function () {
  clearInterval(poopInterval); // Stops the interval after 3 seconds
}, 3000);
```

---

## **Key Differences Between `setTimeout` and `setInterval`**

| Feature              | `setTimeout`                     | `setInterval`                 |
|----------------------|----------------------------------|-------------------------------|
| Purpose              | Executes once after a delay     | Executes repeatedly at intervals |
| Stops Automatically? | Yes                             | No, must use `clearInterval()` |

---

These notes summarize how to use and control timers and intervals effectively. Let me know if further examples or explanations are needed!
