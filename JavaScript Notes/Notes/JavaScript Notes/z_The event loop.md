# Understanding the Event Loop in JavaScript

The **Event Loop** is a fundamental concept in JavaScript, enabling asynchronous operations despite its single-threaded nature. It allows JavaScript to perform non-blocking I/O by offloading tasks to the browser or Node.js environment.

---

## Key Concepts

1. **Single-Threaded Nature**:
   - JavaScript is single-threaded, meaning it can execute only one task at a time in the **call stack**.
   - Some programming languages are multi-threaded, capable of executing multiple processes simultaneously.

2. **Components of the Event Loop**:
   - **Call Stack**:
     - Tracks function calls. The function at the top of the stack is currently being executed.
   - **Web APIs**:
     - Provided by the browser (e.g., `setTimeout`, DOM events). These handle asynchronous tasks.
   - **Callback Queue**:
     - Holds tasks waiting to be added back to the call stack for execution.
   - **Microtask Queue**:
     - Holds high-priority tasks like resolved Promises. These are executed before the callback queue tasks.


---

## How the Event Loop Works

### Example Code:
```js
console.log('Starting');
setTimeout(() => {
  console.log('Running');
}, 2000);
console.log('Ending');
```
### Execution Steps:

1. The `console.log('Starting')` is added to the call stack and executed.
2. The `setTimeout` function is added to the call stack, and its callback is sent to the **Web APIs** with a 2-second timer.
3. The `console.log('Ending')` is added to the call stack and executed.
4. After 2 seconds, the callback from `setTimeout` is added to the **callback queue**.
5. The Event Loop checks if the call stack is empty, then moves the callback to the call stack for execution.
### Output:
```js
Starting
Ending
Running
```

---
## **Callback Hell**

- Occurs when multiple nested callbacks are required, leading to deeply indented, hard-to-read, and maintain code.
- Also referred to as "Pyramid of Doom" or "Christmas Tree Code."

### Example:

```js
doTask1(() => {
  doTask2(() => {
    doTask3(() => {
      console.log('All tasks done!');
    });
  });
});
```

### Solution:

- Use **Promises** or **async/await** to handle asynchronous tasks in a more structured and readable way.

---

## Additional Notes for Interviews

1. **Microtasks vs Macrotasks**:
    
    - **Microtasks**:
        - Include `Promise` callbacks and `MutationObserver`.
        - Executed before any pending macrotasks in the callback queue.
    - **Macrotasks**:
        - Include `setTimeout`, `setInterval`, and `setImmediate` (Node.js).
    - **Execution Order**:
        - Microtasks have higher priority than macrotasks.
        - Example:
```js
console.log('Script start');
setTimeout(() => console.log('setTimeout'), 0);
Promise.resolve().then(() => console.log('Promise resolved'));
console.log('Script end');
```
Output:
```js
Script start
Script end
Promise resolved
setTimeout
```

2. **Blocking the Event Loop**:

- Long-running operations or infinite loops block the Event Loop, causing the application to become unresponsive.
- Example:
```js
while (true) {
  console.log('Blocked!');
}
```
3. **Why Does JavaScript Have an Event Loop?**:
    
    - Enables asynchronous behavior despite being single-threaded.
    - Offloads I/O tasks and timers to the browser or Node.js environment.
      
4. **Common Questions**:
    
    - Explain the difference between the **call stack** and the **callback queue**.
    - What is the **order of execution** for `setTimeout`, `Promise`, and synchronous code?
    - How does the Event Loop handle blocking operations?



---
### **1. Explain the difference between the call stack and the callback queue.**

- **Call Stack**: A data structure where JavaScript tracks the function currently being executed. Functions are added to the stack when called and removed when completed.
- **Callback Queue**: A queue holding asynchronous tasks (e.g., `setTimeout` callbacks) that are ready to execute once the call stack is empty.
- **Key Difference**: The call stack is for currently executing code, while the callback queue holds tasks waiting to be executed.

---

### **2. What is the order of execution for `setTimeout`, `Promise`, and synchronous code?**

1. **Synchronous code** runs first (added to the call stack immediately).
2. **Microtasks (e.g., `Promise.then`)** are executed next, after the synchronous code.
3. **Macrotasks (e.g., `setTimeout`)** are executed last, after the microtasks.

**Example**:
```js
console.log('Start');

setTimeout(() => console.log('setTimeout'), 0);

Promise.resolve().then(() => console.log('Promise'));

console.log('End');

```
Output:
```js
Start
End
Promise
setTimeout
```

---

### **3. How does the Event Loop handle blocking operations?**

- **Blocking operations** (e.g., long loops or heavy computations) prevent the Event Loop from processing other tasks because JavaScript is single-threaded.
- When the call stack is occupied with a blocking operation, no other code (e.g., asynchronous callbacks) can execute, leading to unresponsive applications.
- **Solution**: Use asynchronous APIs (e.g., `setTimeout`, `Web Workers`) to offload heavy computations and avoid blocking the main thread.