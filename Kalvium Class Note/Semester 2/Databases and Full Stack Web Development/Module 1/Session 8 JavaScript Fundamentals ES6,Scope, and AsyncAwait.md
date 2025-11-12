# 📘 1.8 JavaScript Fundamentals: ES6+, Scope, and Async/Await — Detailed Notes

---

## 🔹 Overview

Modern JavaScript (ES6+) is the foundation of full-stack development.  
These features make code **clean**, **efficient**, and **modern** — critical for handling APIs, databases, and async operations.

---

## 🧩 Part 1: Variables & Scope

### 🧠 What is Scope?

**Scope** defines where variables can be accessed or modified in your program.

|Keyword|Scope Type|Reassignable|Hoisted|Best Practice|
|---|---|---|---|---|
|`var`|Function scope|✅ Yes|✅ Yes (undefined value)|❌ Avoid – legacy, causes bugs|
|`let`|Block scope `{}`|✅ Yes|🚫 No|✅ Use when value changes|
|`const`|Block scope `{}`|❌ No|🚫 No|✅ Default choice (use by default)|

---

### 📄 Example

```js
if (true) {
  var a = 10;    // function-scoped
  let b = 20;    // block-scoped
  const c = 30;  // block-scoped
}

console.log(a); // ✅ Works
console.log(b); // ❌ Error: not defined
console.log(c); // ❌ Error: not defined
```

✅ **Best Practice:**

- Use `const` for variables that don’t need reassignment.
- Use `let` when you must reassign.
- Avoid `var` entirely.

---

### 🧩 Example Use-Case

```js
const API_URL = "https://api.example.com";
let retries = 0;
retries++; // valid (let allows reassignment)

```

---

## ⚡ Part 2: Arrow Functions

### 🔸 Purpose

Arrow functions provide **shorter syntax** and **lexical `this` binding** (inherit `this` from their surrounding context).

### 🔹 Syntax Forms

```js
// Traditional
function greet(name) {
  return "Hello, " + name;
}

// Arrow function
const greet = (name) => `Hello, ${name}`;

// No parameter
const getTime = () => new Date().toISOString();
```

---

### 💼 Real Use: Array Methods

```js
const products = [
  { name: "Laptop", price: 1200, inStock: true },
  { name: "Phone", price: 800, inStock: false },
  { name: "Tablet", price: 500, inStock: true },
];

const affordable = products
  .filter(p => p.inStock)
  .filter(p => p.price < 1000)
  .map(p => p.name);

console.log(affordable); // ["Tablet"]
```

🧠 **Why Use Arrow Functions:**

- Short, readable.
- Useful for callbacks and functional operations (`map`, `filter`, `reduce`).

---

## 💬 Part 3: Template Literals

### 🔹 Features

- Use **backticks (`` ` ``)** instead of quotes.
- Allow **multi-line strings**.
- Support **variable interpolation** with `${}`.

### 🔹 Example

```js
const user = { name: "Alice", age: 28 };
const greeting = `Hi ${user.name}, you are ${user.age} years old.`;
```

```js
const html = `
  <h1>Welcome, ${user.name}!</h1>
  <p>Age: ${user.age}</p>
`;
```

💡 **Also:** You can embed expressions:

```js
 `Total: $${(price * 1.08).toFixed(2)}` 
```

---

## 🧮 Part 4: Essential Array Methods

These are the **core of modern JS data handling**.

|Method|Purpose|Example|
|---|---|---|
|`.map()`|Transform each item|`[1,2,3].map(x => x*2)` → `[2,4,6]`|
|`.filter()`|Keep items that pass condition|`[1,2,3,4].filter(x => x%2===0)` → `[2,4]`|
|`.reduce()`|Combine to a single value|`[1,2,3].reduce((a,b)=>a+b,0)` → `6`|

---

### 🧩 Real Example

```js
const fruits = ["apple", "banana", "apple", "orange", "banana", "apple"];

const count = fruits.reduce((acc, fruit) => {
  acc[fruit] = (acc[fruit] || 0) + 1;
  return acc;
}, {});

console.log(count); // { apple: 3, banana: 2, orange: 1 }

```

---

## ⏳ Part 5: Asynchronous JavaScript (Async/Await)

### 🧠 Why It Matters

- JS runs on a **single thread**.
- To avoid blocking, async operations (like API calls) use **Promises** or **async/await**.

---

### ⚠️ The Problem: Callback Hell

```js
fetchUser(id, (user) => {
  fetchOrders(user.id, (orders) => {
    fetchDetails(orders[0].id, (details) => {
      console.log(details);
    });
  });
});
```

Nested callbacks → unreadable, hard to maintain.

---

### ✅ The Fix: Promises

```js
fetchUser(id)
  .then(user => fetchOrders(user.id))
  .then(orders => fetchDetails(orders[0].id))
  .then(details => console.log(details))
  .catch(err => console.error(err));

```

---

### 🚀 The Modern Way: async/await

```js 
async function getUserDetails(id) {
  try {
    const user = await fetchUser(id);
    const orders = await fetchOrders(user.id);
    const details = await fetchOrderDetails(orders[0].id);
    return details;
  } catch (error) {
    console.error(error);
  }
}
```

---

### 🧩 Real Example: Fetch API

```js
async function getUser(id) {
  try {
    const res = await fetch(`https://api.example.com/users/${id}`);
    if (!res.ok) throw new Error(res.status);
    const user = await res.json();
    return user;
  } catch (err) {
    console.error("Failed:", err);
    return null;
  }

```

---

### ⚡ Parallel Execution with Promise.all()

```js
const [user, posts, comments] = await Promise.all([
  fetchUser(1),
  fetchPosts(1),
  fetchComments(1)
]);
```

✅ Runs all async tasks simultaneously — faster.

---

## 🧱 Mini Integration Example

```js
const products = [
  { id: 1, name: "Laptop", price: 1200, category: "electronics" },
  { id: 2, name: "Phone", price: 800, category: "electronics" },
  { id: 3, name: "Desk", price: 300, category: "furniture" },
];

const fetchProducts = () =>
  new Promise(resolve => setTimeout(() => resolve(products), 1000));

async function getAffordableElectronics(maxPrice) {
  const all = await fetchProducts();
  const results = all
    .filter(p => p.category === "electronics" && p.price <= maxPrice)
    .map(p => `${p.name} - $${p.price}`);
  const total = results.reduce((sum, p) => sum + parseInt(p.match(/\d+/)[0]), 0);
  return { results, total };
}

const { results, total } = await getAffordableElectronics(1000);
console.log(results, total);

```

---

## 🧠 Practice Project: Student Grade Manager

```js
const students = [
  { name: "Alice", scores: [85, 90, 92], isActive: true },
  { name: "Bob", scores: [60, 65, 70], isActive: false },
  { name: "Charlie", scores: [95, 88, 91], isActive: true },
];

async function getTopStudents() {
  const data = await new Promise(res => setTimeout(() => res(students), 500));
  return data
    .filter(s => s.isActive)
    .map(s => ({
      name: s.name,
      avg: s.scores.reduce((a, b) => a + b, 0) / s.scores.length
    }))
    .filter(s => s.avg > 70);
}

getTopStudents().then(console.log);

```

---

## 🧾 Quick Reference Sheet

|Concept|Key Point|Example|
|---|---|---|
|`const`|Default variable type|`const url = "..."`|
|`let`|Reassignable variable|`let count = 0`|
|Arrow Fn|Compact syntax|`const add = (a,b)=>a+b`|
|Template Literals|Interpolated strings|`` `Hi ${name}` ``|
|`.map()`|Transform|`[1,2].map(x=>x*2)`|
|`.filter()`|Select|`[1,2,3].filter(x=>x>1)`|
|`.reduce()`|Aggregate|`[1,2,3].reduce((a,b)=>a+b)`|
|`async/await`|Handle async code cleanly|`await fetchData()`|
|`Promise.all()`|Run tasks in parallel|`await Promise.all([...])`|

---

## 📘 Summary

- `const`, `let` provide modern variable control.
- Arrow functions make syntax concise and handle `this` lexically.
- Template literals simplify dynamic string construction.
- `.map()`, `.filter()`, `.reduce()` are essential for data handling.
- Async operations are central in modern JS — use `async/await` for clarity.