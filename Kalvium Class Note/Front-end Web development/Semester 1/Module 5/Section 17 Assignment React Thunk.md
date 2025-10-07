### ✅ `App.jsx`

```js
// src/App.jsx

import React from 'react';
import { useSelector, useDispatch } from 'react-redux';
import { fetchGreeting } from './greetingSlice';

export default function App() {
  const dispatch = useDispatch();

  // Safely select the greeting slice
  const slice = useSelector((state) => (state && state.greeting) || {});

  // Extract possible greeting keys (to handle different slice structures)
  const greeting =
    slice.greeting ?? slice.message ?? slice.value ?? slice.data ?? null;

  // Extract loading and error flags with safe defaults
  const loading = slice.loading ?? false;
  const error = slice.error ?? false;

  // Fetch greeting only once
  const handleClick = () => {
    if (!greeting) {
      dispatch(fetchGreeting());
    }
  };

  return (
    <section role="region" aria-label="greeting section">
      <h2 id="greeting-title">Greeting App</h2>

      {/* Show button only when greeting not yet loaded */}
      {!greeting && (
        <button
          onClick={handleClick}
          disabled={!!loading}
          aria-busy={!!loading}
        >
          Load Greeting
        </button>
      )}

      {/* Show loading state */}
      {loading && <p role="status">Loading...</p>}

      {/* Show greeting text if loaded */}
      {greeting && <p>{greeting}</p>}

      {/* Show error if API failed */}
      {error && <p role="alert">Failed to load greeting</p>}
    </section>
  );
}

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