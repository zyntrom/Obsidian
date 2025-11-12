# **1.24 — Side Effects and Data Fetching with the `useEffect` Hook**

---

## **1. Concept of Side Effects**

### **Definition**

In React, a **side effect** is any operation that affects something outside the component’s rendering logic.  
Rendering is _pure_ (same input → same output).  
Side effects are _impure_ — they interact with external systems.

### **Examples of Side Effects**

|Type|Example|
|---|---|
|Data Fetching|API requests, database calls|
|Timers|`setTimeout()`, `setInterval()`|
|Subscriptions|WebSocket, event listeners|
|DOM Updates|Changing `document.title`|
|Storage|Using `localStorage`, `sessionStorage`|
|Analytics|Logging user actions|

> 🔸 **Why Separate Side Effects?**  
> React’s rendering must remain predictable.  
> Side effects can cause unpredictable behavior if mixed with rendering.

---

## **2. The React Component Lifecycle**

|Stage|Description|
|---|---|
|**Mount**|Component is created and inserted into the DOM|
|**Update**|Component re-renders due to state/prop change|
|**Unmount**|Component is removed from the DOM|

→ **useEffect** allows you to execute code at these points in the lifecycle.

---

## **3. The `useEffect` Hook — Syntax and Behavior**

### **Basic Syntax**

```js
useEffect(() => {
  // Side effect logic here
  console.log("Effect executed");
}, [dependencies]);

```

### **Parts**

1. **Effect function** → the callback where the side effect occurs
2. **Dependency array** → determines _when_ the effect runs

---

## **4. Dependency Array — Control Mechanism**

|Dependency Array|When it Runs|Use Case|
|---|---|---|
|_(none)_|After every render|Rarely used|
|`[]`|Once after initial mount|Fetching data on load|
|`[var1, var2]`|When any listed variable changes|Data refetch or update logic|

> 🧠 **Rule:**  
> Run this effect when any variable inside the dependency array changes.

---

## **5. Data Fetching Pattern with `useEffect`**

### **Example: Fetching API Data Once on Mount**

```js
function UserProfile() {
  const [user, setUser] = useState(null);
  const [loading, setLoading] = useState(true);

  useEffect(() => {
    fetch('https://api.example.com/user')
      .then(res => res.json())
      .then(data => {
        setUser(data);
        setLoading(false);
      });
  }, []); // Runs once on mount

  if (loading) return <p>Loading...</p>;
  return <h1>Hello, {user.name}!</h1>;
}

```

### **Flow**

1. Component mounts → effect runs → fetch begins
2. While fetching → loading UI displays
3. When data arrives → state updates → component re-renders

---

## **6. Simulated Asynchronous Operation (Mock Fetch)**

```js
function SimulatedFetch() {
  const [data, setData] = useState('');
  const [loading, setLoading] = useState(true);

  useEffect(() => {
    const timer = setTimeout(() => {
      setData('Here is your simulated data!');
      setLoading(false);
    }, 2000);
  }, []);

  return (
    <div>
      {loading ? <p>Loading...</p> : <h2>{data}</h2>}
    </div>
  );
}

```
→ `setTimeout` mimics delayed asynchronous data fetching.

---

## **7. Cleanup Functions — Preventing Memory Leaks**

### **Concept**

When a component unmounts, active effects (like timers, listeners, or subscriptions) may continue running.  
To stop this, React allows you to return a **cleanup function** from `useEffect`.

### **Example**

```js
useEffect(() => {
  const timer = setTimeout(() => console.log('Timer fired!'), 1000);

  return () => {
    clearTimeout(timer);
    console.log('Timer cleaned up!');
  };
}, []);

```

**Cleanup Triggers When:**

- The component unmounts
- The effect re-runs due to dependency changes

**Rule:**  
If you set something up inside an effect → clean it up before the next run or before unmounting.

---

## **8. Real-World Example — Auto-Saving Form**

```js
function AutoSaveForm() {
  const [text, setText] = useState('');

  useEffect(() => {
    if (text) {
      localStorage.setItem('draft', text);
      console.log('Draft saved');
    }
  }, [text]); // Runs whenever text changes

  return (
    <textarea
      value={text}
      onChange={(e) => setText(e.target.value)}
      placeholder="Your text auto-saves..."
    />
  );
}

```

→ Automatically saves draft data whenever the user types.

---

## **9. The Loading Pattern (Industry Standard)**

### **Complete Data Fetch Flow**

```js
function DataComponent() {
  const [data, setData] = useState(null);
  const [loading, setLoading] = useState(true);
  const [error, setError] = useState(null);

  useEffect(() => {
    setLoading(true);
    fetch('https://api.example.com/data')
      .then(res => res.json())
      .then(result => {
        setData(result);
        setLoading(false);
      })
      .catch(err => {
        setError(err.message);
        setLoading(false);
      });
  }, []);

  if (loading) return <p>Loading...</p>;
  if (error) return <p>Error: {error}</p>;
  return <Display data={data} />;
}

```
### **Three States**

|State|Meaning|UI Display|
|---|---|---|
|loading = true|Fetch in progress|Loading spinner or text|
|error ≠ null|Fetch failed|Error message|
|data ≠ null|Success|Show fetched content|

---

## **10. The `useEffect` Execution Flow**

```bash
Component mounts → useEffect runs
Effect sets up (e.g., fetch/timer)
Async task finishes → state updates
Component re-renders
If unmounted → cleanup executes

```

---

## **11. Common Mistakes**

|Mistake|Why It’s Wrong|Correct Fix|
|---|---|---|
|❌ Missing dependency array|Runs every render|Add `[]` or relevant deps|
|❌ Forgetting cleanup|Causes memory leaks|Return cleanup function|
|❌ Wrong initial state|Incorrect UI render|Initialize state properly|
|❌ Ignoring errors|App crashes on failure|Add `try/catch` or `.catch()`|
|❌ Using setState after unmount|Causes warnings|Use cleanup to prevent it|

---

## **12. Quick Reference Cheat Sheet**

|Pattern|Code|
|---|---|
|**Run once (on mount)**|`useEffect(() => {...}, []);`|
|**Run when variable changes**|`useEffect(() => {...}, [value]);`|
|**With cleanup**|`useEffect(() => { setup(); return cleanup; }, []);`|
|**Data fetch flow**|`loading → fetch → setData → done`|
|**Dependency array meaning**|`[]` → once, `[x]` → when x changes|

---

## **13. Summary**

✅ `useEffect` handles **side effects** like data fetching, subscriptions, and timers  
✅ **Dependency array** controls _when_ the effect executes  
✅ **Cleanup functions** prevent memory leaks  
✅ Combine `useState` + `useEffect` to manage **loading**, **error**, and **data** states  
✅ Always validate dependencies and clean up resources