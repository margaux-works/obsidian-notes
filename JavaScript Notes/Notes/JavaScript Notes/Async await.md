# Async/Await in JavaScript

**Async/Await** provides a modern syntax to handle asynchronous code, making it cleaner and easier to read compared to Promises or callback-based code. It is built on top of Promises.

---

## Key Concepts

1. **Async Function**:
   - An `async` function always returns a Promise.
   - The `await` keyword can only be used inside an `async` function.
   - Example:
```js
async function example() {
  return "Hello";
}
example().then(console.log); // "Hello"
```
---

2. **Await Keyword**:
   - Pauses the execution of the `async` function until the Promise is resolved or rejected.
   - Simplifies chaining of asynchronous operations.
   - Example:
```js
function wait(ms = 1000) {
  return new Promise((resolve) => setTimeout(resolve, ms));
}

async function run() {
  console.log("Starting...");
  await wait(2000); // Pauses for 2 seconds
  console.log("Done!");
}

run();
// Output:
// Starting...
// (2-second delay)
// Done!
```

---

3. **Error Handling**:
   - Use `try...catch` blocks to handle errors in `async` functions.
   - Example:
```js
async function fetchData() {
  try {
    const response = await fetch("https://api.example.com/data");
    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.error("Error fetching data:", error);
  }
}

fetchData();
```

---

4. **Parallel Execution**:
   - To execute multiple Promises concurrently, use `Promise.all` with `await`.
   - Example:
```js
async function fetchParallel() {
  const [user, posts] = await Promise.all([
    fetch("https://api.example.com/user").then((res) => res.json()),
    fetch("https://api.example.com/posts").then((res) => res.json()),
  ]);
  console.log(user, posts);
}

fetchParallel();
```

---

5. **Sequential Execution**:
   - Await can be used in sequence when the order of execution matters.
   - Example:
```js
async function fetchSequential() {
  const user = await fetch("https://api.example.com/user").then((res) => res.json());
  const posts = await fetch("https://api.example.com/posts").then((res) => res.json());
  console.log(user, posts);
}

fetchSequential();
```

---

## Important Notes for Interviews

1. **Why Async/Await?**
   - Provides a synchronous-like syntax for asynchronous code.
   - Avoids the complexity of `.then()` chaining in Promises.
   - Handles errors more gracefully with `try...catch`.

2. **Common Pitfalls**:
   - Forgetting to mark a function as `async` leads to the error: *"await is only valid in async functions."*
   - Using `await` inside loops can lead to performance issues if tasks can be executed in parallel.

3. **Alternatives**:
   - Async/Await works with Promises but does not replace them.
   - Use `Promise.all` or `Promise.race` when dealing with multiple asynchronous operations.

4. **Real-World Use Cases**:
   - Fetching data from APIs.
   - Reading files or interacting with databases in Node.js.
   - Performing delayed or timed operations.

---
