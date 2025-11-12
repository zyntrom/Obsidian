# 🧠 Redux & Redux Toolkit – I (Full Notes for Exam)

---

## 🔹 What Is Redux?

**Redux** is a **predictable state container** for JavaScript apps — a **centralized “brain”** that manages global state.

### 🧩 In Simple Terms:

- Redux keeps all the app’s state in **one single store**.
- The **data flow is unidirectional** → state updates only when an **action** is dispatched → handled by **reducers** → updates **store** → **UI re-renders**.

---

## 🔹 Why Redux Is Needed

### Without Redux:

- You pass props everywhere (prop drilling).
- Multiple `useState` hooks — confusion.
- One change breaks other components.

### With Redux:

- **Single source of truth** → store.
- **Actions** describe _what_ happens.
- **Reducers** describe _how_ it changes.
- **Components** subscribe to only what they need.

---

## 🔹 Core Principles of Redux

### 1️⃣ Store

- Holds **entire app state**.
- Access state using `getState()`.
- Update state using `dispatch(action)`.

👉 Modern way:  
Use **`configureStore()`** from Redux Toolkit instead of `createStore()`.

```js
import { configureStore } from '@reduxjs/toolkit';
import todosReducer from './todosSlice';

const store = configureStore({
  reducer: {
    todos: todosReducer
  }
});

```
✅ Advantages:

- Redux DevTools enabled automatically.
- Middleware configured automatically.
- Cleaner, easier setup.

---

### 2️⃣ Actions

- Plain **JS objects** describing _what happened_.

Example:

```js
{
  type: 'ADD_TODO',
  payload: { id: 1, text: 'Learn Redux' }
}

```

Dispatched like:

```js
store.dispatch({ type: 'ADD_TODO', payload: { id: 1, text: 'Learn Redux' } });

```

🧾 **Parts of an Action:**

- `type` → mandatory (unique string identifier).
- `payload` → optional (data to update state).

---

### 3️⃣ Reducers

- **Pure functions** that decide **how** the state changes.
- Must:
    - Be **pure** (no side effects / API calls / randomness)
    - **Not mutate** state → must return **new** state.

Example:

```js
function todos(state = [], action) {
  switch (action.type) {
    case 'ADD_TODO':
      return [...state, action.payload];
    default:
      return state;
  }
}

```

---

## 🔹 Unidirectional Data Flow (Redux Flow)

```js
UI → dispatch(action) → reducer → new state → UI re-renders
```

✅ Predictable and traceable (great for debugging).

---

## 🔹 Redux Toolkit (RTK) — Modern Redux

**Redux Toolkit** is the **official, recommended way** to write Redux code.

### ✨ Why Use RTK?

- Eliminates boilerplate.
- Auto-generates **action creators** and **types**.
- Supports **immutability** automatically using **Immer**.
- Includes built-in **async logic tools**.
- Better developer experience (less code, fewer mistakes).

---

## 🔸 Main Features in RTK

### 1️⃣ `configureStore()`

- Creates the Redux store.
- Combines reducers automatically.
- Sets up Redux DevTools + Middleware by default.

Example:

```js
const store = configureStore({
  reducer: {
    todos: todosReducer,
    user: userReducer
  }
});

```

---

### 2️⃣ `createSlice()`

- Combines **actions + reducers** together for one feature.
- Automatically creates:
    - **Action types**
    - **Action creators**
    - **Reducer function**

Example:

```js
import { createSlice } from '@reduxjs/toolkit';

const todosSlice = createSlice({
  name: 'todos',
  initialState: [],
  reducers: {
    addTodo(state, action) {
      state.push({ id: action.payload.id, text: action.payload.text, completed: false });
    },
    toggleTodo(state, action) {
      const todo = state.find(t => t.id === action.payload);
      if (todo) todo.completed = !todo.completed;
    }
  }
});

export const { addTodo, toggleTodo } = todosSlice.actions;
export default todosSlice.reducer;

```

💡 Under the hood:

- Uses **Immer** → you can “mutate” state safely.
- Exports actions automatically → no manual types.

---

### 3️⃣ `createAsyncThunk()`

Used for **async operations** (like API calls).

Example:

```js
import { createAsyncThunk } from '@reduxjs/toolkit';

export const fetchTodos = createAsyncThunk('todos/fetchTodos', async () => {
  const res = await fetch('/api/todos');
  return await res.json();
});

```

It auto-generates **three lifecycle actions**:

- `fetchTodos.pending`
- `fetchTodos.fulfilled`
- `fetchTodos.rejected`

🎯 Benefit:  
No more writing extra async boilerplate (request, success, error manually).

---

## 🔹 Analogy: Redux as City Traffic Control 🚦

|Concept|Analogy|
|---|---|
|**Redux**|Central Traffic Controller|
|**Store**|Control Room|
|**Actions**|Traffic Signals|
|**Reducers**|Traffic Lights responding to signals|

Without a controller, traffic → chaos.  
Without Redux, app state → chaos.

---

## 🔹 When to Use Redux

✅ Use Redux when:

- Many components need shared state (e.g., authentication, cart, user data).
- State updates are complex.
- You want predictable, centralized state control.

🚫 Avoid Redux when:

- App is small or simple.
- Local state (`useState` / `useContext`) is enough.

---

## 🔹 Real-World Example: E-Commerce App 🛒

|Feature|Redux Usage|
|---|---|
|**ProductList**|Load products using `createAsyncThunk()`|
|**Cart**|Manage add/remove using `cartSlice`|
|**Checkout**|Access shared cart + user state|
|**Selectors**|Extract specific parts of state efficiently|

✅ Each “feature” (cart, user, products) → one **slice**.

---

## 🔹 Summary Table

|Concept|Description|Function|
|---|---|---|
|**Store**|Central place holding app state|`configureStore()`|
|**Action**|Describes what happened|`{ type, payload }`|
|**Reducer**|Updates state based on action|Pure function|
|**createSlice()**|Combines actions + reducers|Less boilerplate|
|**createAsyncThunk()**|Handles async logic|API calls|
|**Redux DevTools**|Debugging + time travel|Built-in with RTK|

---

## 🧾 Key Rules & Best Practices

1. **Reducers are pure** → no async code inside.
2. **Never mutate state directly** (except inside RTK slices using Immer).
3. **Use multiple slices** for modularity (cartSlice, userSlice, etc.).
4. **Dispatch actions** to change state, never modify state directly in components.
5. **Use selectors** to access only needed data from store.

---

## 🧠 Quick Revision Summary

- Redux = predictable state management
- 3 pillars: **Store, Actions, Reducers**
- Data flow = **one way (unidirectional)**
- RTK makes Redux:
    - Easier to set up
    - Less code-heavy
    - Async-friendly
- Key APIs:  
    `configureStore()`, `createSlice()`, `createAsyncThunk()`
- Use Redux for **large, complex, multi-component apps**