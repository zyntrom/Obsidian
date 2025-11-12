# 🧠 Kalvium AL 1.19 — State Management with the `useState` Hook

## 1️⃣ Introduction – Why Components Need Memory

- In React, **functional components** are _pure functions_ — they receive **props** and return **JSX** (UI output).
- However, they are **stateless** by default:  
    → Meaning they cannot _remember_ what happened before a re-render.
- For **interactive UIs**, components must _remember data_ (like a counter value or user input).
- This “memory” is called **state**, and we manage it using the **`useState` Hook**.

---

## 2️⃣ The Problem — Stateless Components

### Example: A “Broken” Counter Using Normal Variable

```js
function BrokenCounter() {
  let count = 0;

  function handleClick() {
    count = count + 1;
    console.log("New count:", count);
  }

  return (
    <div>
      <h1>Count: {count}</h1>
      <button onClick={handleClick}>Increment</button>
    </div>
  );
}

```

### What Happens

- Clicking the button **updates the variable** `count`, but **UI doesn’t update**.
    
- Because React:
    
    - Runs the component function **once per render**.
        
    - **Does not track** local variables.
        
    - **Renders once**, then discards all local variables.
        

### Key Takeaway

> Changing a normal variable **does not trigger re-render** in React.  
> Only **state changes** can trigger a re-render.

---

## 3️⃣ What is “State”?

- **State** = Component’s private, reactive memory.
    
- React **watches** state variables for changes.
    
- When state changes, React:
    
    1. **Updates** the state value internally.
        
    2. **Re-renders** the component.
        
    3. **Updates the UI** with the new data.
        

---

## 4️⃣ React Hooks — Introducing `useState`

### Definition

> A **Hook** is a special React function that allows you to “hook into” React features (like state or lifecycle) from functional components.

### Syntax

`import { useState } from 'react';  function MyComponent() {   const [stateVariable, setStateVariable] = useState(initialValue); }`

### Explanation of Syntax

|Term|Meaning|
|---|---|
|`useState(initialValue)`|Hook function that creates a state variable with a default value.|
|`[stateVariable, setStateVariable]`|**Array Destructuring** – extracts two elements returned by `useState`:  <br>1️⃣ The current state value.  <br>2️⃣ The function to update it.|
|`setStateVariable(newValue)`|Updates state and triggers a **re-render**.|
|`initialValue`|Used only during first render; ignored after that.|

---

## 5️⃣ Understanding How `setState` Works

Calling the setter function (`setCount` in this case):

1. **Schedules an update:** tells React to store a new value for this piece of state.
    
2. **Triggers a re-render:** React re-runs the component with the new value, producing new JSX.
    
3. **Updates the UI:** old output is replaced with the new one.
    

---

## 6️⃣ The Working Counter Example

`import { useState } from 'react';  function WorkingCounter() {   const [count, setCount] = useState(0);    function handleClick() {     setCount(count + 1);   }    return (     <div>       <h1>Count: {count}</h1>       <button onClick={handleClick}>Increment</button>     </div>   ); }`

### Step-by-Step Breakdown

|Step|What Happens|
|---|---|
|1|`useState(0)` creates state: count = 0|
|2|UI renders “Count: 0”|
|3|User clicks → `handleClick()` runs|
|4|`setCount(count + 1)` tells React to update count|
|5|React re-renders component with `count = 1`|
|6|UI updates → shows “Count: 1”|

---

## 7️⃣ Props vs State — The Core Difference

|Feature|**Props**|**State**|
|---|---|---|
|Source|Passed from parent component|Declared inside component|
|Ownership|Controlled by parent|Owned by the component itself|
|Mutability|Read-only|Mutable (changeable using setter)|
|Purpose|Configure component from outside|Handle dynamic, interactive data|
|Example|`<Welcome name="Alen" />`|`const [count, setCount] = useState(0)`|

### Quick Activity

Decide if each belongs to **props** or **state**:

|Data|Belongs To|
|---|---|
|User ID passed to component|Props|
|"Follow" button toggle (Follow/Following)|State|
|User name from parent list|Props|
|Text user is typing in input box|State|

---

## 8️⃣ Example: Light Switch Component

`import { useState } from 'react';  function LightSwitch() {   const [isOn, setIsOn] = useState(false);    const handleToggle = () => {     setIsOn(!isOn);   };    return (     <div className="light-switch-box">       <p>The light is currently {isOn ? "ON" : "OFF"}</p>       <button onClick={handleToggle}>Toggle Light</button>     </div>   ); }`

### Concept Breakdown

|Concept|Explanation|
|---|---|
|**Boolean State**|`useState(false)` manages true/false data easily.|
|**Toggling State**|`setIsOn(!isOn)` switches between ON/OFF.|
|**Conditional Rendering**|`{isOn ? "ON" : "OFF"}` changes displayed text dynamically.|
|**State Re-render**|Clicking button → setter updates value → React re-renders UI.|

---

## 9️⃣ Key Rules of `useState`

1. Must be called **inside the top level** of a functional component (not inside loops or conditions).
    
2. Can be used **multiple times** in one component for multiple states.
    
3. **Never modify state directly** (`count = 5 ❌`).  
    Always use the setter function (`setCount(5) ✅`).
    
4. **Re-render** happens automatically — no need to manually update the DOM.
    

---

## 🔟 Summary – Core Takeaways

|Concept|Summary|
|---|---|
|**State**|Component’s internal, private memory.|
|**`useState()`**|React Hook that enables state in functional components.|
|**Setter Function**|Only valid way to update state and trigger re-render.|
|**Props vs State**|Props = external configuration; State = internal memory.|
|**Re-render Logic**|Changing state → React re-runs component → updates UI.|

---

## 🔹 Quick Command Recap

|Action|Code|
|---|---|
|Import Hook|`import { useState } from 'react';`|
|Declare state|`const [count, setCount] = useState(0);`|
|Read state|`{count}`|
|Update state|`setCount(count + 1);`|
|Toggle boolean|`setIsOn(!isOn);`|

---

## 🔹 Reference Links

- [React Official Docs – State: A Component’s Memory](https://react.dev/learn/state-a-components-memory)
    
- [React Official Docs – useState Hook](https://react.dev/reference/react/useState)