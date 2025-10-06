# 🧠 6.15 — Assignment | Redux Toolkit Counter App

---

## 🎯 Learning Goals

By the end of this assignment, you will understand how to:

1. Create and configure a Redux slice
2. Manage global state using Redux Toolkit
3. Connect Redux to React with `Provider`
4. Access and update Redux state using hooks
5. Build a simple interactive UI with `useSelector` and `useDispatch`

---

## 🔹 Concepts Recap

### 1️⃣ **Redux Slice**

A slice = **state + reducers + actions** for a single feature.

We’ll make a slice called `counterSlice`:

- `initialState`: `{ count: 0 }`
- Reducers: `increment`, `decrement`

```js
import { createSlice } from "@reduxjs/toolkit";

const counterSlice = createSlice({
  name: "counter",
  initialState: { count: 0 },
  reducers: {
    increment: (state) => { state.count += 1 },
    decrement: (state) => { state.count -= 1 }
  }
});

export const { increment, decrement } = counterSlice.actions;
export default counterSlice.reducer;

```

---

### 2️⃣ **Store Configuration**

The store holds your app’s **global Redux state**.

We use `configureStore()` (from Redux Toolkit).

```js
import { configureStore } from "@reduxjs/toolkit";
import counterReducer from "./counterSlice";

const store = configureStore({
  reducer: {
    counter: counterReducer
  }
});

export default store;

```

---

### 3️⃣ **Provider**

`Provider` from `react-redux` connects the store to your React app.

```js
import { Provider } from "react-redux";
import store from "./store";

<Provider store={store}>
  <App />
</Provider>

```

_(In this assignment, we’ll do everything inside `App.jsx`, so the Provider can be used here too.)_

---

### 4️⃣ **React-Redux Hooks**

To connect React components with Redux state:

|Hook|Purpose|
|---|---|
|`useSelector()`|Reads data from Redux store|
|`useDispatch()`|Sends (dispatches) actions to Redux store|

Example:

```js
const count = useSelector((state) => state.counter.count);
const dispatch = useDispatch();

```

---

## 💻 The Assignment: Counter App

### 🧾 Requirements

- Display: `Count: 0` initially
- Two buttons: `Increment` and `Decrement`
- Clicking “Increment” → increases count
- Clicking “Decrement” → decreases count
- Must use Redux Toolkit, **no `useState` allowed**

---

## ✅ Full Working Code (Edit only `src/App.jsx`)

```js
import React from "react";
import { Provider, useSelector, useDispatch } from "react-redux";
import { createSlice, configureStore } from "@reduxjs/toolkit";

// Step 1: Create a slice
const counterSlice = createSlice({
  name: "counter",
  initialState: { count: 0 },
  reducers: {
    increment: (state) => {
      state.count += 1;
    },
    decrement: (state) => {
      state.count -= 1;
    },
  },
});

const { increment, decrement } = counterSlice.actions;

// Step 2: Configure the store
const store = configureStore({
  reducer: {
    counter: counterSlice.reducer,
  },
});

// Step 3: Create the Counter component
function Counter() {
  const count = useSelector((state) => state.counter.count);
  const dispatch = useDispatch();

  return (
    <div style={{ textAlign: "center", marginTop: "50px" }}>
      <p>Count: {count}</p>
      <button onClick={() => dispatch(increment())}>Increment</button>
      <button onClick={() => dispatch(decrement())}>Decrement</button>
    </div>
  );
}

// Step 4: Wrap with Provider and render
export default function App() {
  return (
    <Provider store={store}>
      <Counter />
    </Provider>
  );
}

```

---

## ✅ What This Code Does

|Step|Explanation|
|---|---|
|**1. Create Slice**|Defines `count` in global state with reducers `increment`, `decrement`.|
|**2. Configure Store**|Registers the `counter` reducer.|
|**3. Counter Component**|Uses hooks to access and update Redux state.|
|**4. Provider**|Makes the store available throughout the app.|

---

## 🧪 What Will Be Tested

|Test|Expected Result|
|---|---|
|Initial display|`Count: 0`|
|Click Increment|Increases by 1|
|Click Decrement|Decreases by 1|
|Buttons visible|Both rendered|
|After 3 increments|Shows `Count: 3`|

Command to test:

`npm run test:serve`

---

## ❌ Restrictions Recap

- ❌ Do **not** use `useState`
- ❌ Do **not** hardcode count
- ❌ Do **not** change button text
- ❌ Do **not** modify test file
- ✅ Edit only `src/App.jsx`

---

## 💡 Extra Notes (Exam & Viva Tips)

|Concept|Short Explanation|
|---|---|
|**Redux Toolkit**|Simplifies Redux setup with less code.|
|**Slice**|Combines state, reducers, and actions.|
|**Reducer**|Decides how state changes.|
|**Action**|Tells what happened (e.g., “increment”).|
|**Store**|Central place that holds app’s state.|
|**Provider**|Makes the Redux store available to components.|
|**useSelector**|Reads state from Redux store.|
|**useDispatch**|Sends actions to Redux store.|
|**Immer**|Allows writing state updates like mutation safely.|

---

## 🧭 Summary Cheat Sheet

|Step|Function|Purpose|
|---|---|---|
|`createSlice()`|Create slice with reducers & actions|Logic|
|`configureStore()`|Create global store|Data center|
|`<Provider store={store}>`|Give store to app|Connection|
|`useSelector()`|Read Redux state|Read|
|`useDispatch()`|Dispatch actions|Write|

---

✅ **Final Output Example:**

`Count: 0 [Increment] [Decrement]`

- After 3 increments → `Count: 3`
- After 1 decrement → `Count: 2`