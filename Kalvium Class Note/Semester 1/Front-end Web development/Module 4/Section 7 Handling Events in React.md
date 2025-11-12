# Handling Events in React

## Learning Goals

By the end of this topic, you can:

- ✅ Handle **events** like `click`, `submit`, `change` in React
- ✅ Understand **Synthetic Events** and why React uses them
- ✅ Build **interactive components** using event handlers

---

## Analogy: Events in Real Life

- Imagine being in a **restaurant**:
    - You **raise your hand** to call the waiter → **event**
    - The waiter **responds** and comes over → **event handler**
- Similarly in React:
    - User interacts with UI (clicks, types, submits) → **event**
    - React runs a function (event handler) → **response**

---

## Event Handling in HTML vs React

### In HTML

```html
<button onclick="doSomething()">Click me</button>
```

- Uses **lowercase** `onclick`
- Calls function via string

### In React

```html
<button onClick={handleClick}>Click me</button>
```

- Uses **camelCase** `onClick`
- Passes **function directly** (not a string)
- Cleaner, safer, React-style

---

## Example: Click Counter

- **Event**: User clicks button
- **Handler**: `handleClick` function
- **Effect**: Counter state increases using `setCount`

### Key Breakdown

- `handleClick` = function that updates state
- Passed to `onClick` as `{handleClick}`
- Runs **only when clicked**

⚠️ Important:

- `onClick={handleClick}` → ✅ correct (function reference)
- `onClick={handleClick()}` → ❌ wrong (executes immediately on render)

---

## Synthetic Events in React

- **Definition**: React wraps native browser events in a **SyntheticEvent** object.
- **Why?** To make event handling consistent across browsers.
- **Analogy**: Like a **universal remote** → one button works on all TVs (browsers).

### Features:

- Cross-browser compatibility
- Provides event details like:
    - `event.target` → element that triggered event
    - `event.type` → type of event (click, submit, etc.)
    - `event.pageX / pageY` → mouse coordinates
- Supports `event.preventDefault()` to stop default browser actions

---

## Key React Events

- **onClick** → Button clicks
- **onChange** → Input changes
- **onSubmit** → Form submissions
- **onMouseOver / onMouseOut** → Hover effects

---
```embed
title: "ReactJS Tutorial - 13 - Event Handling"
image: "https://i.ytimg.com/vi/Znqv84xi8Vs/maxresdefault.jpg"
description: "📘 Courses - https://learn.codevolution.dev/💖 Support UPI - https://support.codevolution.dev/💖 Support PayPal - https://www.paypal.me/Codevolution💾 Github..."
url: "https://youtu.be/Znqv84xi8Vs"
favicon: ""
aspectRatio: "56.25"
```

```embed
title: "ReactJS Tutorial - 14 - Binding Event Handlers"
image: "https://i.ytimg.com/vi/kVWpBtRjkCk/maxresdefault.jpg"
description: "📘 Courses - https://learn.codevolution.dev/💖 Support UPI - https://support.codevolution.dev/💖 Support PayPal - https://www.paypal.me/Codevolution💾 Github..."
url: "https://youtu.be/kVWpBtRjkCk"
favicon: ""
aspectRatio: "56.25"
```

## Summary

- React handles user interactions with **event handlers**.
- Event names use **camelCase** (`onClick`, `onChange`, `onSubmit`).
- Handlers are passed as **functions** (not strings).
- React uses **SyntheticEvent** to standardize behavior across browsers.
- You can extract details like target, type, and coordinates from the event object.
- Essential for building **interactive UI elements** (forms, modals, validation, etc.).

---

## Resources

- React Official Docs: Event Handling
- Why We Use Synthetic Events in React – GeeksForGeeks

---