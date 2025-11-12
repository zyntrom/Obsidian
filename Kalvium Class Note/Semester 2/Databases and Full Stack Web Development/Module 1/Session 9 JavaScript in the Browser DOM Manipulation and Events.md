# 🧠 **Kalvium AL 1.9 — JavaScript in the Browser: DOM Manipulation and Events**

---

## **1. Understanding the DOM (Document Object Model)**

### **Definition**

- The **DOM** is a **tree-like structure** that represents an HTML document.
- It allows JavaScript to **access, modify, add, or remove elements** dynamically.

### **Key Points**

- Each HTML tag becomes a **Node** in the DOM tree.
- Nodes can be:
    - **Element Nodes** (e.g., `<div>`, `<p>`)
    - **Text Nodes** (text inside an element)
    - **Attribute Nodes** (like `class`, `id`)

### **Purpose**

- DOM manipulation lets JS **change a webpage after it’s loaded** — no refresh required.
- Common tasks:
    - Selecting elements
    - Editing content or styles
    - Adding/removing elements
    - Responding to user actions (clicks, typing, etc.)

---

## **2. Selecting DOM Elements**

### **a. `querySelector()`**
- Returns **the first element** that matches a CSS selector.

```js
const btn = document.querySelector('button');
const header = document.querySelector('#main-header');
const card = document.querySelector('.card');
const firstLink = document.querySelector('nav ul li:first-child a');
```

> ✅ Use this when selecting **one element**.

---

### **b. `querySelectorAll()`**

- Returns **all elements** matching the selector as a **NodeList**.
    

```js
const buttons = document.querySelectorAll('button');
buttons.forEach(btn => console.log(btn.textContent));
```

> ✅ Use when you need to select **multiple elements**.

|Method|Returns|Use Case|
|---|---|---|
|`querySelector()`|First matching element|Single target|
|`querySelectorAll()`|NodeList of all matches|Multiple elements|

---

## **3. Manipulating Element Content**

### **a. `innerHTML`**
- Replaces or gets **all HTML** inside an element.

```js
container.innerHTML = '<h2>New Content!</h2><p>Everything replaced.</p>';
```

> ⚠️ Risky if inserting user input — can allow XSS attacks.

---

### **b. `textContent`**

- Safely updates or retrieves **only the text** of an element.

```js
title.textContent = 'New Safe Title';
```
> ✅ Preferred for **text-only** updates (no HTML parsing).

---

### **c. `classList`**

- Efficiently manages CSS classes.

```js
box.classList.add('active');
box.classList.remove('hidden');
box.classList.toggle('dark-mode');
box.classList.contains('active'); // returns true/false
```

|Method|Description|
|---|---|
|`add()`|Adds a class|
|`remove()`|Removes a class|
|`toggle()`|Adds/removes automatically|
|`contains()`|Checks if present|

---

## **4. Creating and Inserting Elements**

### **a. Create Elements**

```js
const newDiv = document.createElement('div');
newDiv.textContent = 'I am new!';
newDiv.classList.add('cool-div');
```

### **b. Add to DOM**

```js
document.querySelector('.container').appendChild(newDiv);
```

### **c. Insertion Methods**

|Method|Position|Example|
|---|---|---|
|`appendChild()`|End of parent|`parent.appendChild(child)`|
|`prepend()`|Beginning|`parent.prepend(child)`|
|`before()`|Before element|`element.before(newEl)`|
|`after()`|After element|`element.after(newEl)`|
```embed
title: "The JavaScript DOM explained in 5 minutes! 🌳"
image: "https://i.ytimg.com/vi/NO5kUNxGIu0/maxresdefault.jpg"
description: "#JavaScript #tutorial #course// DOM = DOCUMENT OBJECT MODEL//              Object{} that represents the page you see in the web browser //              and p..."
url: "https://youtu.be/NO5kUNxGIu0"
favicon: ""
aspectRatio: "56.25"
```

---

## **5. Event Handling**

### **Definition**

- **Events** are actions (clicks, key presses, submissions) users perform.
- **Event listeners** make JS respond to these actions.

---

### **a. `addEventListener()` Syntax**

```js
element.addEventListener('eventType', callbackFunction);
```
---

### **b. Common Event Types**

|Event Type|Description|Example|
|---|---|---|
|`click`|Mouse click|`button.addEventListener('click', fn)`|
|`submit`|Form submission|`form.addEventListener('submit', fn)`|
|`input`|Typing/input change|`input.addEventListener('input', fn)`|
|`mouseenter`|Mouse enters element|`div.addEventListener('mouseenter', fn)`|
|`mouseleave`|Mouse leaves element|`div.addEventListener('mouseleave', fn)`|

---

### **c. Click Event Example**

```js
button.addEventListener('click', () => {
    alert('Button clicked!');
});
```

---

### **d. Form Event Example**

```js
form.addEventListener('submit', (e) => {
    e.preventDefault(); // stop page reload
    console.log('Form submitted!');
});
```

---

### **e. Input Event Example**

```js
searchBox.addEventListener('input', (e) => {
    console.log(e.target.value);
});
```

---

### **f. Mouse Events Example**

```js
box.addEventListener('mouseenter', () => box.classList.add('hovered'));
box.addEventListener('mouseleave', () => box.classList.remove('hovered'));
```

---

## **6. Event Object**

Each event listener automatically receives an **event object**.

```js
button.addEventListener('click', (e) => {
    console.log(e.target);    // element clicked
    console.log(e.type);      // 'click'
    console.log(e.clientX);   // X position
    e.preventDefault();       // stops default action
    e.stopPropagation();      // prevents bubbling
});
```

|Property|Meaning|
|---|---|
|`target`|Element that triggered event|
|`type`|Event type name|
|`clientX / clientY`|Mouse position|
|`preventDefault()`|Stops default behavior|
|`stopPropagation()`|Stops bubbling to parents|

---

## **7. Mini Projects**

### **Project 1: Interactive Todo**

```js
addButton.addEventListener('click', () => {
  const li = document.createElement('li');
  li.textContent = todoInput.value;
  li.classList.add('todo-item');
  li.addEventListener('click', () => li.remove());
  todoList.appendChild(li);
  todoInput.value = '';
});
```

### **Project 2: Dark Mode Toggle**

```js
toggleButton.addEventListener('click', () => {
  document.body.classList.toggle('dark-mode');
  toggleButton.textContent =
    document.body.classList.contains('dark-mode')
      ? '☀️ Light Mode'
      : '🌙 Dark Mode';
});
```

### **Project 3: Form Validation**

```js
form.addEventListener('submit', (e) => {
  e.preventDefault();
  const email = emailInput.value;

  if (!email.includes('@')) {
    errorMsg.textContent = 'Enter a valid email';
    errorMsg.classList.add('visible');
    emailInput.classList.add('error');
  } else {
    errorMsg.classList.remove('visible');
    emailInput.classList.remove('error');
  }
});

```

---

## **8. Counter App (Assignment Summary)**

### **Goal**

A counter with **Increment**, **Decrement**, and **Reset** buttons.

### **Steps**

```js
function setupCounterApp() {
  const countDisplay = document.getElementById('count');
  const incrementBtn = document.getElementById('increment');
  const decrementBtn = document.getElementById('decrement');
  const resetBtn = document.getElementById('reset');

  let count = 0;

  const updateDisplay = () => {
    countDisplay.textContent = count;
  };

  incrementBtn.addEventListener('click', () => { count++; updateDisplay(); });
  decrementBtn.addEventListener('click', () => { count--; updateDisplay(); });
  resetBtn.addEventListener('click', () => { count = 0; updateDisplay(); });

  updateDisplay();
}
```

### **Checklist**

✅ Starts at 0  
✅ All 3 buttons work  
✅ Uses `getElementById()`  
✅ Uses `textContent` (not `innerHTML`)  
✅ Properly indented and clean

---

## **9. Quick Reference Cheat Sheet**

|Task|Method|Example|
|---|---|---|
|Find element|`querySelector()`|`document.querySelector('.box')`|
|Find all|`querySelectorAll()`|`document.querySelectorAll('button')`|
|Change text|`textContent`|`el.textContent = 'New text'`|
|Change HTML|`innerHTML`|`el.innerHTML = '<p>Hi</p>'`|
|Add class|`classList.add()`|`el.classList.add('active')`|
|Remove class|`classList.remove()`|`el.classList.remove('hidden')`|
|Toggle class|`classList.toggle()`|`el.classList.toggle('dark')`|
|Create element|`createElement()`|`document.createElement('div')`|
|Add element|`appendChild()`|`parent.appendChild(child)`|
|Add event|`addEventListener()`|`btn.addEventListener('click', fn)`|
|Stop default|`preventDefault()`|`e.preventDefault()`|

---

## **10. Key Technical Tips**

- Use **`const`** for DOM elements.
- Use **arrow functions** for clean callbacks.
- Always check `if (element)` before modifying.
- Prefer **`classList`** over direct `className` changes.
- Use **`preventDefault()`** in form events.
- Debug using `console.log()` at key points.