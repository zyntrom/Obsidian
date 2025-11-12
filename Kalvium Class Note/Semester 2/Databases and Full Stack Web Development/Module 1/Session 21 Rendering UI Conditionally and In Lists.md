# 🧠 Kalvium AL 1.21 — Rendering UI Conditionally & In Lists

---

## 🔹 1. Introduction: From Static to Dynamic UIs

In React, **conditional rendering** and **list rendering** allow you to create dynamic UIs that adapt based on data or user state.

A static component always looks the same.  
A dynamic component **responds** to logic — for example:

- Showing “Welcome back!” when logged in.
- Showing “Please log in.” when logged out.
- Displaying a list of 100 products using data, not 100 hardcoded elements.

React achieves this with **JavaScript expressions** and **data mapping**, allowing developers to decide _what_ to show and _how many_ to show — efficiently and declaratively.

---

## 🔹 2. Conditional Rendering

Conditional rendering means showing or hiding certain UI elements **based on conditions** (usually variables or state).  
React allows you to use **regular JavaScript logic** directly inside JSX.

### 🧩 Common Conditional Rendering Methods

---

### ✅ a. Using the `&&` (AND) Operator

Use when you want to render **something only if a condition is true**.

```js
{isLoggedIn && <p>Welcome back!</p>}
```

- If `isLoggedIn` is `true` → shows: “Welcome back!”
- If `false` → renders nothing.
- Good for simple “show-only-if-true” cases.

---

### ✅ b. Using the **Ternary Operator** (`condition ? A : B`)

Use when you want to render **one thing or another** based on a condition.

```js
{isLoggedIn ? <p>Welcome back!</p> : <p>Please log in.</p>}
```

- If true → shows first expression.
- If false → shows second.
- Works inline and is concise for binary decisions.

---

### ✅ c. Using an **if Statement** (outside JSX)

Used for **complex conditions** or **multiple branches**.

```js
function Greeting({ isLoggedIn, username }) {
  if (isLoggedIn && username) {
    return <p>Welcome back, {username}!</p>;
  }
  return <p>Please log in.</p>;
}
```
- Logic is written before the `return`.
- Helps handle nested or multi-condition logic cleanly.

---

### ⚙️ Summary Table — Conditional Rendering

|Technique|Syntax|Use Case|Example|
|---|---|---|---|
|`&&`|`cond && <Component />`|Show element if true|Show greeting if logged in|
|Ternary|`cond ? A : B`|Two outcomes|Login vs logout text|
|if-statement|`if(...) return ...`|Complex/multi-logic|Conditional returns|

---

## 🔹 3. List Rendering

When displaying **multiple similar items**, React uses the `map()` function to render an array of data into a list of elements.

### ✅ a. Basic `map()` Example

```js
const fruits = ['Apple', 'Banana', 'Orange'];

return (
  <ul>
    {fruits.map((fruit, index) => (
      <li key={index}>{fruit}</li>
    ))}
  </ul>
);

```

**How it works:**

- `map()` loops through the array.
- For each item, it returns JSX (`<li>`).
- React merges all returned elements into one list.

---

### ✅ b. Using Objects with Unique Keys

Always prefer **unique identifiers** instead of array indexes for `key`.

```js
const items = [
  { id: 1, name: 'Apple' },
  { id: 2, name: 'Banana' }
];

return (
  <ul>
    {items.map(item => (
      <li key={item.id}>{item.name}</li>
    ))}
  </ul>
);

```

---

## 🔹 4. The Importance of the `key` Prop

`key` is a special prop React uses to track each item in a list.

### 🧠 Why It Matters

- Helps React **identify which elements changed, added, or removed.**
- Prevents unnecessary re-renders.
- Improves rendering **performance**.
- Prevents UI bugs when items are reordered.

### ⚠️ Rules

- Must be **unique** among siblings.
- Should be **stable** (not derived from index if data changes order).
- Do **not** use random values (like `Math.random()`).

---

### ✅ Example with Keys in Dynamic Lists

```js
const users = [
  { id: 101, name: 'Asha' },
  { id: 102, name: 'Ravi' }
];

return (
  <div>
    {users.map(user => (
      <p key={user.id}>{user.name}</p>
    ))}
  </div>
);

```

---

## 🔹 5. Combining Conditional & List Rendering

Real apps often use **both** concepts together — show lists _only if_ data exists.

```js
function ProductList({ products }) {
  if (!products || products.length === 0) {
    return <p>No products available.</p>;
  }

  return (
    <ul>
      {products.map(product => (
        <li key={product.id}>{product.name}</li>
      ))}
    </ul>
  );
}
```

Explanation:

- Checks if list is empty before mapping.
- Prevents errors from mapping over `undefined`.
- Ensures proper fallback UI.

---

## 🔹 6. Advanced Example — Dynamic Greeting + Item List

```js
function App() {
  const isLoggedIn = true;
  const username = "Sarah";
  const items = ["Apples", "Bananas", "Oranges"];

  return (
    <div>
      {/* Conditional Rendering */}
      {isLoggedIn ? (
        <h2>Welcome back, {username}!</h2>
      ) : (
        <button>Please Log In</button>
      )}

      {/* List Rendering */}
      <h3>Shopping List:</h3>
      {items.length > 0 ? (
        <ul>
          {items.map((item, index) => (
            <li key={index}>{item}</li>
          ))}
        </ul>
      ) : (
        <p>Your cart is empty.</p>
      )}
    </div>
  );
}
```

This combines:

- **Ternary** for user greeting.
- **List rendering** for item display.
- **Condition check** for empty list fallback.

---

## 🔹 7. Best Practices Summary

|Concept|Best Practice|Reason|
|---|---|---|
|Conditional UI|Keep logic simple in JSX|Improves readability|
|Complex logic|Move outside `return`|Cleaner JSX|
|List rendering|Always use `.map()`|Declarative and efficient|
|`key` prop|Use stable unique IDs|React performance|
|Empty states|Always handle missing/empty arrays|Prevent runtime errors|

---

## 🔹 8. Mini Checklist Before You Code

✅ Know which part of UI depends on conditions.  
✅ Choose between `&&`, `?:`, or `if` based on complexity.  
✅ Always return valid JSX for all branches.  
✅ When rendering arrays, wrap items with a unique `key`.  
✅ Handle empty data gracefully.

---

## 🔹 9. Key Takeaways

- **Conditional Rendering** = Dynamic decision-making in JSX.
- **List Rendering** = Efficiently displaying repetitive data using `map()`.
- **`key` Prop** = Identifies list items uniquely for React’s reconciliation.
- Together, they form the **core of dynamic UIs** in modern React apps.

```embed
title: "Static vs Dynamic Websites - What's the Difference?"
image: "https://i.ytimg.com/vi/_wFJj94kSTU/maxresdefault.jpg"
description: "What are static webpages? What are dynamic ones? What's the difference and which approach should you follow? This video should clear some doubts and help you..."
url: "https://youtu.be/_wFJj94kSTU"
favicon: ""
aspectRatio: "56.25"
```

---

## 🔹 10. References

1. React Docs – [Conditional Rendering](https://react.dev/learn/conditional-rendering)
2. React Docs – [Rendering Lists](https://react.dev/learn/rendering-lists)
3. MDN – [Array.map()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)