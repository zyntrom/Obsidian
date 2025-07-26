### 🧠 **Quick Revision Notes – DOM Manipulation: Selecting Elements**

---

#### ✅ **Learning Objectives**

- Understand what the **DOM** is.
- Learn how to **select HTML elements** using JavaScript.
- Practice **changing content, attributes, and styles** dynamically.
- Learn how to **add and remove HTML elements** with code.

---

#### 🌳 **What is the DOM (Document Object Model)?**

- It’s a **tree-like structure** representing your webpage.
- Each **HTML element** is a **node** in this tree.
- JavaScript uses the DOM to **access and modify** HTML elements dynamically.

---

#### 🔥 **Why is the DOM Important?**

- Enables **dynamic** and **interactive** webpages.
- Lets you:
    - Update content without reloading the page.
    - React to user actions (clicks, typing, etc.).
    - Add animations, effects, or change styles.
    - Build single-page applications (SPAs).

---

#### 🔍 **Selecting HTML Elements in JavaScript**

```js 
document.getElementById("id")
```
- Selects **a single element** by its `id`.

```js
const element = document.getElementById("myId");
```

```js
 document.getElementsByClassName("className")
```

- Selects **all elements** with the same class.
- Returns an **HTMLCollection**.

```js
const elements = document.getElementsByClassName("myClass");
```

```js
document.getElementsByTagName("tag")
```

- Selects **all elements** with a specific tag (e.g., `p`, `div`).
- Returns an **HTMLCollection**.

```js
const paragraphs = document.getElementsByTagName("p");
```

```js
document.querySelector("CSS selector")
```

- Selects the **first matching element**.
- Follows **CSS-style selectors**.

```js
const element = document.querySelector(".className");
```

```js
document.querySelectorAll("CSS selector")
```

- Selects **all matching elements**.
- Returns a **NodeList**.

```js
const elements = document.querySelectorAll("p.className");
```

---

### 📝 **Summary**

|Method|What It Does|Returns|
|---|---|---|
|`getElementById()`|Select by unique ID|Single element|
|`getElementsByClassName()`|All elements with class|HTMLCollection|
|`getElementsByTagName()`|All elements with tag|HTMLCollection|
|`querySelector()`|First element by CSS selector|Single element|
|`querySelectorAll()`|All elements by CSS selector|NodeList|