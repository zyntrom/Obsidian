# JavaScript – Event Loop

## 🎯 Learning Goals

- Recall how **JavaScript code executes** (call stack).
- Understand the **Event Loop** and its role in async behavior.
- Learn the difference between **microtasks** and **macrotasks**.
- Debug execution order in async code.

---

## 🔹 1. JavaScript Execution Model

- **JavaScript is single-threaded** → executes **one task at a time**.
- Execution is managed with a **Call Stack**.

### Call Stack

- Keeps track of function calls.
- Works in **LIFO (Last In, First Out)** order.

Example:

```js
function greet() {   
	console.log("Hello!"); 
} 
function sayGoodbye() {   
	console.log("Goodbye!"); 
} 
greet(); 
sayGoodbye();
```

Execution:

1. `greet()` pushed → runs → popped.
2. `sayGoodbye()` pushed → runs → popped.

✔ **Only one function executes at a time.**

---

## 🔹 2. The Event Loop

Even though JS is single-threaded, it can handle **asynchronous tasks** (like timers, promises, events) using the **Event Loop**.

### How it works:

1. **Call Stack** runs all synchronous code.
2. Async tasks go to the **Web APIs (browser / Node.js env)**.
3. Completed async tasks are queued:
    - **Microtask Queue** → High priority (Promises, MutationObserver).
    - **Macrotask Queue** → Lower priority (setTimeout, setInterval, events).
4. **Event Loop** constantly checks:
    - If stack is empty → take tasks from **microtask queue** first.
    - Then take tasks from **macrotask queue**.
```embed
title: "How does event loop work? -- Event Loop Visualized"
image: "https://i.ytimg.com/vi/3Jma9VYvSz8/maxresdefault.jpg?sqp=-oaymwEmCIAKENAF8quKqQMa8AEB-AH-CYAC0AWKAgwIABABGDogXShyMA8=&rs=AOn4CLAJUSxp_AUVYffbA3YNb4X1sgnq8w"
description: "Knowing how JavaScript is running behind the browser's screen is essential to understanding the behavior of a program on the web. This video shows a deep exp..."
url: "https://youtu.be/3Jma9VYvSz8"
favicon: ""
aspectRatio: "56.25"
```

---

## 🔹 3. Code Examples

### Example 1 – Basic Event Loop

```js
console.log("Start"); 
setTimeout(() => console.log("Timeout"), 2000); 
console.log("End");

```
Output:

```
Start End Timeout   (after 2 sec)
```

✔ `setTimeout` runs later, not immediately.

---

### Example 2 – Microtasks vs Macrotasks

```js
console.log("Start"); 
Promise.resolve().then(() => console.log("Microtask")); 
setTimeout(() => console.log("Macrotask"), 0); 
console.log("End");
```

Output:

```
Start End Microtask Macrotask
```

✔ **Microtasks (Promises) run before Macrotasks (setTimeout).**

---

## 🔹 4. Analogy – Chef & Orders 🍳

- **Call Stack** → Orders being cooked right now.
- **Message Queue (Macrotasks)** → Orders waiting in the line (timers, events).
- **Microtask Queue** → Urgent VIP orders (Promises).
- **Event Loop** → The chef’s assistant managing order flow.

---

## 🔹 5. Practice

### Example A

```js
console.log("Order Placed"); 
setTimeout(() => console.log("Preparing Order"), 0); Promise.resolve().then(() => console.log("Order Confirmed")); console.log("Order Completed");
```

Output:

```
Order Placed Order Completed Order Confirmed Preparing Order
```

---

### Example B

```js
console.log("A"); 
setTimeout(() => console.log("B"), 1000); 
setTimeout(() => console.log("C"), 0); 
console.log("D");
```

Output:

```
A D C B
```

✔ Because `setTimeout(..., 0)` is still async → goes to macrotask queue.

---

### Debug Challenge

Reorder so **Task 3 runs last**:

```js
console.log("Task 1"); 
setTimeout(() => console.log("Task 2"), 0); 
Promise.resolve().then(() => console.log("Task 3"));
```

Actual Output:

```
Task 1 
Task 3 
Task 2
```

✔ Because Promise (microtask) runs before `setTimeout` (macrotask).

---

## 🔹 6. Key Takeaways

- JS is **single-threaded**, but async is handled via **Event Loop**.
- **Call Stack** runs sync code first.
- **Microtasks (Promises) > Macrotasks (setTimeout)**.
- Event Loop ensures smooth async handling.

---

✅ Mastering Event Loop = smoother debugging of async JS.