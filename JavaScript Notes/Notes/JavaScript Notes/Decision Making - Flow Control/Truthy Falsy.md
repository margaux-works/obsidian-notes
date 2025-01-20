### Truthy Falsy


- A value is considered "truthy" if it evaluates to `true` in a Boolean context.
- A value is considered "falsy" if it evaluates to `false` in a Boolean context.

| Truthy values |     Falsy values     |
| :-----------: | :------------------: |
|       1       |          0           |
|    -10<br>    |  undefined variable  |
|  full string  | variable set as null |
| string of "0" |   empty string ""    |
|  empty array  |         null         |
| empty object  |         NaN          |

## **Usage in Decision Making**

### **Implicit Coercion**

JavaScript automatically converts values to `true` or `false` in conditional statements.

```js
let userName = ""; // Falsy value if (userName) {     console.log("Welcome, user!"); } else {     console.log("Please log in."); }`

**Output:** `Please log in.`
```

### **Using Logical Operators**

Logical operators can also handle truthy and falsy values:

- `&&` returns the first falsy value or the last truthy value.
- `||` returns the first truthy value or the last falsy value.


```js
let name = "";  let defaultName = name || "Guest"; console.log(defaultName); // "Guest"`
```

## **Best Practices**

1. Use truthy and falsy checks for quick, concise conditionals.
2. Be careful with falsy values like `0` or `""` if they have valid meanings in your context.