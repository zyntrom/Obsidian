# 🧠 Redux & Redux Toolkit – II (Full Notes + Concept Explanations)

---

## 🔹 Quick Recap: Redux Toolkit

Redux Toolkit (RTK) = The **official, simplified way** to use Redux.  
It removes all the repetitive “boilerplate” code and gives you clean APIs like:

- `createSlice()`
- `configureStore()`
- `createAsyncThunk()`

---

## 🔸 Learning Objectives

By the end of this topic, you should be able to:

- Understand **Slices** and how they organize Redux logic.
- Write and manage **Reducers** that update state predictably.
- Handle **asynchronous (async)** actions using `createAsyncThunk()`.
- Know **when** and **why** to use Redux Toolkit in real projects.

---

## 🔹 What Are Slices in Redux Toolkit?

Think of a **slice** like a “folder” that contains:

- The **state** for one feature
- The **reducers** that modify it
- The **actions** used to trigger changes

### 🧩 Definition:

> A “slice” is a self-contained module of Redux logic for a specific feature of your app.

### 🧱 Example:

```js
import { createSlice } from '@reduxjs/toolkit';

const counterSlice = createSlice({
  name: 'counter',            // Name of this slice
  initialState: { value: 0 }, // Initial state
  reducers: {                 // Functions to update state
    increment: state => { state.value += 1 },
    decrement: state => { state.value -= 1 }
  }
});

export const { increment, decrement } = counterSlice.actions;
export default counterSlice.reducer;

```

### 💡 Key Points:

- Each slice is responsible for _one part_ of the global state (e.g., user, todos, cart).
- Redux Toolkit **auto-generates** action creators and action types.
- You can write “mutating” code safely because RTK uses **Immer** under the hood (it makes immutable copies automatically).

### 🔍 Example Use Case:

If you made a **cartSlice** for an online store, it might have:

- State: `cartItems`, `totalPrice`
- Actions: `addItem`, `removeItem`, `clearCart`

---

## 🔹 What Are Reducers?

Reducers = the **pure functions** that actually **update the state** in response to actions.

### 🧠 Rules of Reducers:

1. Take **current state** and an **action** as input.
2. Return **new state** (they never modify the old one directly).
3. **No side effects** — no API calls, random numbers, etc.

### 🧱 Example:

```js
import { createSlice } from '@reduxjs/toolkit';

const todosSlice = createSlice({
  name: 'todos',
  initialState: [],
  reducers: {
    addTodo: (state, action) => {
      const newTodo = {
        id: Date.now(),
        text: action.payload,
        completed: false
      };
      state.push(newTodo); // Looks like mutation, but safe (thanks to Immer)
    },
    toggleTodo: (state, action) => {
      const todo = state.find(todo => todo.id === action.payload);
      if (todo) todo.completed = !todo.completed;
    }
  }
});

export const { addTodo, toggleTodo } = todosSlice.actions;
export default todosSlice.reducer;

```

### 💡 How can this "mutate" safely?

Because **Immer** automatically creates a copy of the state behind the scenes.  
So, even though you write `state.push(...)`, Redux Toolkit keeps the state immutable.

---

## 🔹 Handling Asynchronous Actions (Async Logic)

### ⚙️ The Challenge:

Reducers must be **pure** — they cannot wait for API calls or handle async code.

### 💪 Solution: `createAsyncThunk()`

This function lets you handle **async actions** (like fetching data from APIs) easily.

---

### 🧱 Example: Fetching Users

```js
import { createAsyncThunk, createSlice } from '@reduxjs/toolkit';

// Step 1: Define the async thunk
export const fetchUsers = createAsyncThunk(
  'users/fetchUsers',  // action type prefix
  async () => {
    const response = await fetch('https://api.example.com/users');
    const data = await response.json();
    return data; // This becomes the payload for 'fulfilled'
  }
);

// Step 2: Create the slice
const usersSlice = createSlice({
  name: 'users',
  initialState: {
    users: [],
    loading: false,
    error: null
  },
  reducers: {},

  // Step 3: Handle async states (pending, fulfilled, rejected)
  extraReducers: (builder) => {
    builder
      .addCase(fetchUsers.pending, (state) => {
        state.loading = true;
        state.error = null;
      })
      .addCase(fetchUsers.fulfilled, (state, action) => {
        state.loading = false;
        state.users = action.payload;
      })
      .addCase(fetchUsers.rejected, (state, action) => {
        state.loading = false;
        state.error = action.error.message;
      });
  }
});

export default usersSlice.reducer;

```

---

### 🔄 Async Action Lifecycle

|Stage|Auto-generated Action|Meaning|
|---|---|---|
|**Pending**|`fetchUsers.pending`|API request started|
|**Fulfilled**|`fetchUsers.fulfilled`|Request succeeded, data returned|
|**Rejected**|`fetchUsers.rejected`|Request failed, error thrown|

### 🧠 Summary of Async Flow:

```js
Component → dispatch(fetchUsers()) 
→ (Pending) → API call 
→ (Fulfilled or Rejected) → Reducer updates state → UI re-renders

```

---

## 🔹 extraReducers in createSlice()

Used to handle **actions not defined inside the slice’s reducers**, such as those created by `createAsyncThunk()`.

🧩 Inside the `builder` object:

- `.addCase(actionType, reducerFn)` is used for each async state (pending, fulfilled, rejected).

---

## 🔹 Use Cases for Redux Toolkit

Redux Toolkit shines when your app has **complex, shared, or asynchronous state**.

### 🧭 Common Use Cases:

|Scenario|Why Use RTK?|
|---|---|
|Global state like authentication, theme|Shared across components|
|API data fetching|Use `createAsyncThunk()`|
|Shopping cart, form wizard|Complex state logic|
|Caching / storing fetched data|Centralized state store|

---

## 🔹 Example: Designing a To-Do App with Redux Toolkit

### 🔸 Slices Needed:

1. `tasksSlice` — manages all tasks
2. (Optional) `filterSlice` — manages filter (e.g., “All”, “Completed”)

### 🔸 Actions:

- `addTask`
- `editTask`
- `removeTask`
- `toggleTask`

### 🔸 State Shape Example:

```js
{
  tasks: [
    { id: 1, text: 'Study Redux', done: false },
    { id: 2, text: 'Take exam', done: true }
  ],
  filter: 'all'
}

```

---

## 🔹 Connecting Redux Toolkit with React (Preview)

(You’ll see more in Redux Toolkit III, but remember these now:)

1. Wrap app with `Provider`:

```js
import { Provider } from 'react-redux';
import store from './store';

<Provider store={store}>
  <App />
</Provider>

```

2. Use hooks inside components:

```js
import { useSelector, useDispatch } from 'react-redux';
import { addTodo } from './todosSlice';

const todos = useSelector(state => state.todos);
const dispatch = useDispatch();

dispatch(addTodo("Learn Redux Toolkit"));

```

---

## 🔹 Summary — Wrap Up Like a Burrito 🌯

|Concept|Meaning|Function|
|---|---|---|
|**Slice**|A self-contained feature module|`createSlice()`|
|**Reducer**|Pure function to update state|Inside slice|
|**Action**|Object describing what happened|Auto-created by slice|
|**Async Thunk**|Handles async tasks (APIs)|`createAsyncThunk()`|
|**extraReducers**|Handles external / async actions|builder.addCase()|
|**Immer**|Allows writing “mutating” code safely|Built into RTK|

---

## 🔹 TL;DR for Exams 📝

- Redux Toolkit = official, simplified Redux library.
- `createSlice()` = defines state + actions + reducers in one go.
- Reducers are **pure functions** (safe updates, no side effects).
- Async actions → `createAsyncThunk()` + handled in `extraReducers`.
- Great for global state, API data, and complex logic.
- Avoid using Redux for simple local states.