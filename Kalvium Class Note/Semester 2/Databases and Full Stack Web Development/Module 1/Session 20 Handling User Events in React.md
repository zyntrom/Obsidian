# ⚙️ Kalvium AL 1.20 — Handling User Events in React

All unnecessary metaphors and fluff are removed. Each section is clearly structured, deeply explained, and example-backed for direct recall during exams.

---

## 1️⃣ Introduction — Making Components Interactive

- Static components only **display** information.
- To make apps **interactive**, components must **respond to user actions** such as:
    - Clicks, typing, mouse movement, or key presses.
- These interactions are called **events**.
- React provides a **synthetic event system** that allows components to “listen” and **respond** to these user actions.

**Goal:**  
Implement interactive behavior in React using **event handlers** such as `onClick`, `onChange`, `onSubmit`, etc.

---

## 2️⃣ Event Handling in React vs HTML

|Concept|HTML|React|
|---|---|---|
|Event name|lowercase (`onclick`)|camelCase (`onClick`)|
|Value|String code (`onclick="alert('Hi')"`)|Function reference (`onClick={handleClick}`)|
|Binding syntax|Inline JS in quotes|Curly braces `{}` to embed JS expressions|
|Execution|Runs directly when parsed|Called only when the event occurs|

### Example:

```html
// HTML way
<button onclick="alert('Hi')">Click</button>

// React way
<button onClick={handleClick}>Click</button>

```
### Common React Event Handlers

|Event|Typical Use|
|---|---|
|`onClick`|Button press, toggles, actions|
|`onChange`|Input or select field changes|
|`onSubmit`|Form submission|
|`onMouseEnter` / `onMouseLeave`|Hover effects|
|`onKeyDown` / `onKeyUp`|Keyboard shortcuts|

---

## 3️⃣ Critical Concept — Passing vs Calling a Function

|Code|Description|Correct?|
|---|---|---|
|`onClick={handleClick}`|Passes the function reference → runs _when clicked_|✅|
|`onClick={handleClick()}`|Calls function _immediately during render_|❌ Causes re-renders and bugs|

> **Rule:** Never call a function directly inside an event prop.  
> Always **pass a reference** so React can call it _later_ when the event occurs.

---

## 4️⃣ Defining Event Handler Functions Inside Components

- Define event handlers **inside the same component** they belong to.
- This is called **co-location** — keeping logic and UI together for readability.
- These handlers can access the component’s **state and props**.

### Example: Simple Alert Button

```js
function AlertButton() {
  function handleAlertClick() {
    alert("You clicked the button!");
  }

  return (
    <button onClick={handleAlertClick}>
      Click Me
    </button>
  );
}
```

### Key Notes

- Function names typically follow `handle<Event>` pattern → `handleClick`, `handleChange`, etc.
- Event handlers are **pure JS functions** that React executes when an event occurs.

---

## 5️⃣ Passing Event Handlers as Props (Parent–Child Communication)

This allows a **child component** to trigger behavior defined by its **parent**.

### Concept

- Parent defines **what should happen**.
- Child defines **when it should happen**.
- The handler is **passed as a prop** from parent → child.

---

### Example

#### Child Component (Generic Button)

```js
function Button({ onCustomClick, children }) {
  return (
    <button onClick={onCustomClick}>
      {children}
    </button>
  );
}

```
#### Parent Component

```js
function Toolbar() {
  const handlePlayMovie = () => alert("Playing movie!");
  const handleUploadImage = () => alert("Uploading image!");

  return (
    <div>
      <Button onCustomClick={handlePlayMovie}>Play Movie</Button>
      <Button onCustomClick={handleUploadImage}>Upload Image</Button>
    </div>
  );
}

```

### Analysis

|Concept|Explanation|
|---|---|
|Parent owns logic|`handlePlayMovie`, `handleUploadImage`|
|Child triggers parent function|via prop `onCustomClick`|
|Benefit|Reusable “dumb” components that are easy to customize|

---

## 6️⃣ Accessing Event Information

When an event occurs, React passes a special **SyntheticEvent object** to your handler.

### Definition

> **SyntheticEvent** – React’s cross-browser wrapper around the native browser event object.

- Provides consistent behavior across browsers.
- Contains event data like:
    - `e.target` → The element that triggered the event.
    - `e.target.value` → For inputs, current text value.
    - `e.preventDefault()` → Prevent default browser behavior (e.g., form submission reload).
    - `e.stopPropagation()` → Stop event bubbling to parent elements.

---

### Example: Accessing Event Data

```js
function LogEvent() {
  function handleClick(e) {
    console.log("Event type:", e.type);
    console.log("Target element:", e.target);
  }

  return <button onClick={handleClick}>Log Event</button>;
}

```

---

## 7️⃣ Controlled Components — Combining State and Events

A **controlled component** is an input element whose value is controlled by React state.  
This is the standard pattern for managing form input data.

### Example: Live Typing Component

```js
import { useState } from 'react';

function LiveTyper() {
  const [text, setText] = useState("");

  function handleChange(e) {
    setText(e.target.value);
  }

  return (
    <div>
      <input type="text" value={text} onChange={handleChange} />
      <p>You are typing: {text}</p>
    </div>
  );
}
```

---

### Step-by-Step Flow

|Step|Description|
|---|---|
|1️⃣|User types in input|
|2️⃣|`onChange` triggers → passes event to handler|
|3️⃣|Handler extracts `e.target.value`|
|4️⃣|`setText()` updates React state|
|5️⃣|React re-renders with new `text`|
|6️⃣|Input’s `value` and `<p>` both display updated state|

> This ensures **React is the single source of truth** for the input’s value.

---

## 8️⃣ Common Event Patterns in React

|Purpose|JSX Example|Notes|
|---|---|---|
|Handle Click|`<button onClick={handleClick}>`|For buttons and clickable divs|
|Handle Change|`<input onChange={handleChange}>`|Used for text fields and dropdowns|
|Prevent Default|`<form onSubmit={handleSubmit}>` with `e.preventDefault()`|Avoids page reload|
|Keyboard Input|`<input onKeyDown={handleKey}>`|Detects key presses|
|Mouse Hover|`<div onMouseEnter={fn}>`|Hover effects|

---

## 9️⃣ Key Rules for Event Handling in React

1. **Use camelCase** for all event names (`onClick`, `onChange`).
2. **Pass functions**, never call them directly.
3. Define handler functions **inside components** for access to local state/props.
4. Always use the **SyntheticEvent object** to access event data.
5. For form fields, use **controlled components** — tie input value to state.
6. You can pass handler functions as **props** to child components for reuse.

---

```embed
title: "Handling Events in React.js | onClick, onChange & More Explained with Examples"
image: "https://i.ytimg.com/vi/bEKL_4uEXAo/maxresdefault.jpg"
description: "How Does Event Handling Work in React.js? In this tutorial, you’ll master the fundamentals of event handling in React, including how to respond to user actio..."
url: "https://youtu.be/bEKL_4uEXAo"
favicon: ""
aspectRatio: "56.25"
```

## 🔟 Summary — Core Takeaways

|Concept|Key Point|
|---|---|
|**Events in React**|Handled via synthetic event system.|
|**Function References**|Always pass the function, not call it.|
|**Co-location**|Define handlers inside components.|
|**Passing as Props**|Enables child-to-parent communication.|
|**SyntheticEvent**|Provides cross-browser event object.|
|**Controlled Components**|Keep form input synchronized with state.|

---

## 🔹 Quick Command Recap

|Action|Code|
|---|---|
|Handle button click|`<button onClick={handleClick}>`|
|Get input value|`e.target.value`|
|Prevent default form reload|`e.preventDefault()`|
|Update state on change|`setState(e.target.value)`|
|Pass handler as prop|`<Child onClick={handler} />`|

---

## 🔹 References

- React Docs: [Responding to Events](https://react.dev/learn/responding-to-events)
- React Docs: Event Handlers