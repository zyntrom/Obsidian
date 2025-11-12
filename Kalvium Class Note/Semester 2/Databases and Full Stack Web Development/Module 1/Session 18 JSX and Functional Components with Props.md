# 🧠 JSX & Functional Components with Props — Detailed Notes

---

## 🌟 Lesson Overview

**Main Goal:**  
To learn how to make React pages _dynamic and reusable_ by using **JSX** (JavaScript XML) and **Functional Components** that accept **props (properties)** as input data.

**Outcome:**  
By the end of this topic, you should be able to:
- Understand what **JSX** is and how it differs from HTML.
- Embed JavaScript expressions inside JSX.
- Define **functional components** in React.
- Pass and use **props** between components.
- Use **destructuring** to simplify prop usage.

---

## 🔹 Part 1: Understanding JSX (JavaScript XML)

### 🧩 What is JSX?

- **JSX** = _JavaScript XML_
- It is a **syntax extension for JavaScript** that allows writing HTML-like elements directly inside JS files.
- JSX makes defining UI components easy and readable.

### 💡 Example

#### Without JSX:

```js
React.createElement('h1', null, 'Hello!');
```
#### With JSX:

```html
<h1>Hello!</h1>
```

Both produce the same element, but JSX is more intuitive.

---

### ⚙️ How JSX Works (Behind the Scenes)

- Browsers **cannot read JSX directly**.
- A compiler called **Babel** converts JSX → `React.createElement()` before execution.
- So, you write HTML-like syntax, but React executes plain JavaScript under the hood.

---

### ⚖️ Key Differences Between JSX and HTML

|Concept|HTML|JSX|
|---|---|---|
|**Class Attribute**|`class="box"`|`className="box"` (because `class` is a JS keyword)|
|**Self-closing Tags**|`<img>` or `<br>`|Must end with `/` → `<img />` or `<br />`|
|**Attribute Naming**|kebab-case (e.g., `background-color`)|camelCase (e.g., `backgroundColor`)|

---

### 🧠 Example: Spot the Errors

**Incorrect JSX:**

```js
const profile = <div class="user"><img src="avatar.jpg"></div>;

```
**Corrected JSX:**

```js
const profile = <div className="user"><img src="avatar.jpg" /></div>;
```

✅ Fixed:

1. `class` → `className`
2. `<img>` → `<img />`

---

## 🔹 Part 2: Embedding JavaScript in JSX — `{}`

JSX allows embedding **JavaScript expressions** inside curly braces `{}`.

### 🧩 What is an Expression?

An **expression** is any code that produces a value.  
(e.g., variables, calculations, function calls)

---

### 🧠 Examples

#### 1. Display a Variable

```js
const userName = "Alice"; 
<h1>Hello, {userName}!</h1>
```

👉 Output: `<h1>Hello, Alice!</h1>`

---

#### 2. Run a Calculation

```js
const price = 10;
const tax = 0.05;
<p>Total: ${price * (1 + tax)}</p>
```

👉 Output: `<p>Total: $10.5</p>`

---

#### 3. Combine Logic & Data

```js
const user = { firstName: "Bob", age: 30 };
<p>{user.firstName.toUpperCase()} will be {user.age + 1} next year.</p>
```

👉 Output: **"BOB will be 31 next year."**

---

## 🔹 Part 3: Defining Functional Components

A **Component** = a reusable piece of UI.  
React apps are built from **many small components**.

### 🧩 Functional Component

A **functional component** is just a **JavaScript function** that returns **JSX**.

---

### ✅ Rules of a Functional Component

1. It must be a normal JS function.
2. The **name must start with a capital letter** (e.g., `UserCard`, not `userCard`).
    - React treats lowercase tags as built-in HTML, and capitalized ones as custom components.
3. Must return **one single JSX element** (wrap multiple in a parent `<div>` or fragment `<>...</>`).

---

### 💡 Example

```js
function WelcomeMessage() {
  return (
    <div>
      <h1>Welcome to My App!</h1>
      <p>This is a reusable component.</p>
    </div>
  );
}
```

---

## 🔹 Part 4: Props — Passing Data Between Components

**Props** = _Properties_ → data passed **from a parent component to a child component.**

Think of props as **function parameters** for components.

---

### ⚙️ How Props Work

#### 1. Pass Data from Parent

```js
<UserInfo name="Alice" />
```

#### 2. Receive Data in Child

```js
function UserInfo(props) {
  // props = { name: "Alice" }
  return <h2>{props.name}</h2>;
}
```

---

### 🧠 Key Idea: One-Way Data Flow

- Data in React flows **downward** — from parent → child.
- Props are **read-only** (children cannot modify them).
- This makes React predictable and easier to debug.

---

## 🔹 Part 5: Destructuring Props (Cleaner Syntax)

Instead of writing `props.name` or `props.email` repeatedly, we can _destructure_ props directly in the function parameter.

---

### 💡 Example

#### Without Destructuring

```js
function UserInfo(props) {
  return (
    <div>
      <h2>{props.name}</h2>
      <p>{props.email}</p>
    </div>
  );
}

```

#### ✅ With Destructuring

```js
function UserInfo({ name, email }) {
  return (
    <div>
      <h2>{name}</h2>
      <p>{email}</p>
    </div>
  );
}
```

🧠 Benefit:

- Clearer and shorter code.
- You can immediately see which props the component expects.

---

## 🔹 Part 6: Final Practice — Building a Dynamic Component

**Task:** Create a `Greeting` component that accepts a `name` prop.

### ✅ Solution

```js
function Greeting({ name }) {
  return <h1>Hello, {name}!</h1>;
}

// Usage
<Greeting name="Bob" />

```

**Explanation:**

- `{ name }` destructures the prop directly.
- When rendered, it outputs:  
    → `<h1>Hello, Bob!</h1>`

---

## 📚 Key Takeaways Summary

|Concept|Meaning / Use|
|---|---|
|**JSX**|A syntax to write HTML inside JS (compiled by Babel).|
|**Babel**|Translates JSX into `React.createElement()` before running.|
|**Functional Component**|JS function that returns JSX.|
|**Props**|Data passed from parent → child (read-only).|
|**Destructuring**|Cleaner syntax for using props directly in parameters.|
|**{} (Curly Braces)**|Embed JavaScript expressions inside JSX.|
|**One-Way Data Flow**|Data flows top → down; ensures predictability.|

---

## 🧩 Reference Links

- React Docs: [Writing Markup with JSX](https://react.dev/learn/writing-markup-with-jsx)
- React Docs: [Passing Props to a Component](https://react.dev/learn/passing-props-to-a-component)