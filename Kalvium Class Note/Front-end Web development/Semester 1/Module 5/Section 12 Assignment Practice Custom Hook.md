# 🛠 6.12 Assignment | Custom Hook: useWindowWidth

---

## 🔹 Objective

By the end of this assignment, you will be able to:

1. Understand **custom hooks** in React.
2. Use `useState` and `useEffect` together to manage **state and side effects**.
3. Listen for **window resize events**.
4. Implement **cleanup logic** to avoid memory leaks.
5. Encapsulate logic inside a **reusable hook** (`useWindowWidth`).

---

## 🔹 Task Description

- Build a custom hook `useWindowWidth` that tracks the current width of the browser window.
- Use it inside the `App` component to display the **current window width**.
- Ensure **automatic updates** when the window is resized.
- Properly **clean up** the event listener to avoid memory leaks.

---

## 🔹 Steps to Implement `useWindowWidth`

1️⃣ **Create the custom hook**

```js
import { useState, useEffect } from "react";

function useWindowWidth() {
  const [width, setWidth] = useState(window.innerWidth); // initial width

  useEffect(() => {
    const handleResize = () => setWidth(window.innerWidth); // update state on resize

    window.addEventListener("resize", handleResize); // add listener

    return () => {
      window.removeEventListener("resize", handleResize); // cleanup
    };
  }, []); // empty dependency array → runs once on mount

  return width; // return the current width
}

```

2️⃣ **Use the hook in the App component**

```js
function App() {
  const width = useWindowWidth(); // get the current width

  return (
    <div>
      <h1>Current Window Width: {width}px</h1>
    </div>
  );
}

export default App;

```

---

## 🔹 Key Points

- **`useState`** stores the current window width.
- **`useEffect`** handles the side effect of adding/removing the resize event listener.
- **Cleanup**: Removing the listener in the return function prevents memory leaks.
- The hook **returns the width**, so any component can consume it.
- The `App` component updates automatically whenever the window is resized.

---

## 🔹 Analogy

- **Custom Hook = Smart Observer**: Watches the window width.
- **Component = Display Board**: Shows the width.
- **Effect Cleanup = Disconnect**: Stops listening when the component goes away.

---

## 🔹 Hints Recap

- Initialize state: `useState(window.innerWidth)`
- Update on resize: `handleResize` function
- Listen: `window.addEventListener("resize", handleResize)`
- Cleanup: `window.removeEventListener("resize", handleResize)`
- Return the value: `return width`