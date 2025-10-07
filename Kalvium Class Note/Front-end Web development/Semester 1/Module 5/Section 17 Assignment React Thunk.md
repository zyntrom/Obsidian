### ✅ `App.jsx`

```js
import React from "react";
import { useSelector, useDispatch } from "react-redux";
import { fetchGreeting } from "./greetingSlice";

const App = () => {
  // Access Redux store state
  const greeting = useSelector((state) => state.greeting.greeting);
  const loading = useSelector((state) => state.greeting.loading);
  const error = useSelector((state) => state.greeting.error);

  // Get dispatch to trigger actions
  const dispatch = useDispatch();

  // Handle button click
  const handleClick = () => {
    // Only fetch if no greeting and not loading
    if (!greeting && !loading) {
      dispatch(fetchGreeting());
    }
  };

  return (
    <div style={{ textAlign: "center", marginTop: "40px", fontFamily: "sans-serif" }}>
      {/* Loading State */}
      {loading && <p>Loading...</p>}

      {/* Error State */}
      {error && <p>Failed to load greeting</p>}

      {/* Success State */}
      {greeting && <p>{greeting}</p>}

      {/* Show Button only if greeting not loaded and no error */}
      {!greeting && !error && !loading && (
        <button onClick={handleClick}>Load Greeting</button>
      )}
    </div>
    );
};

export default App;

```

---

### 🧠 Explanation

1. **`useSelector()`**
    - `state.greeting.greeting` → holds the API response (greeting message)
    - `state.greeting.loading` → indicates if API call is ongoing
    - `state.greeting.error` → stores error status if the API fails
2. **`useDispatch()`**
    - Gets the `dispatch` function from Redux
    - Used to call the async thunk `fetchGreeting()`
3. **`handleClick()`**
    - Ensures greeting is fetched only once (no refetch)
    - Dispatches the `fetchGreeting()` thunk
4. **Conditional Rendering**
    - **Button:** shown only before greeting loads
    - **Paragraph (`<p>`):** shows greeting or error message
    - **"Loading..."** is shown during API call
5. **No Re-Fetching**
    - Once greeting is loaded, button disappears

---

### ✅ Output Flow

**Initial:**  
[ Load Greeting Button ]

**On Click:**  
Loading...

**Success:**  
Hello from the API!

**Error (if API fails):**  
Failed to load greeting

---