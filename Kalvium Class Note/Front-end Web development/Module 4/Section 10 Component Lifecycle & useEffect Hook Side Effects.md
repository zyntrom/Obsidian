# 🌟 React Component Lifecycle & `useEffect` Hook

## 🎯 Learning Objectives

By the end, you can:

- Understand **lifecycle phases** of a React component.
- Use **`useEffect`** to manage **side effects**.
- Write **cleanup functions** to prevent memory leaks.
- Fetch data and respond to changes with **`useEffect`**.

---

## 1️⃣ Lifecycle Phases in React

Think of a component like a person at a party:

- **Mounting** → Arriving at the party (component created, inserted into DOM).
- **Updating** → Reacting to changes (state/props update).
- **Unmounting** → Saying goodbye and leaving cleanly (component removed).
### Old way: Class components → lifecycle methods (`componentDidMount`, `componentDidUpdate`, `componentWillUnmount`).

### New way: Functional components → **`useEffect` hook** handles all.

---

## 2️⃣ What is `useEffect`?

- A **hook** for running **side effects** in functional components.
- Examples of side effects:
    - Fetching data
    - Setting up timers
    - Subscribing/unsubscribing to events
    - Manually changing the DOM

### Syntax:

```js
useEffect(() => {   
	// Side effect logic here   
	return () => {     
	// Optional cleanup logic here   
	}; 
}, [dependencies]);
```

### Breakdown:

- **First argument** = effect function (code to run).
- **Second argument** = dependency array:
    - `[]` → runs once on mount (like `componentDidMount`).
    - `[deps]` → runs when any dependency changes (like `componentDidUpdate`).
    - Omit array → runs **after every render**.
- **Return function** = cleanup, runs before unmount or re-run.

---

## 3️⃣ Examples

### a) Run Once on Mount

```js
useEffect(() => {   console.log("Component has mounted!"); }, []);
```

✅ Runs only once → after initial render.

---

### b) Cleanup Function Example (Timer)

```js
useEffect(() => {   
	console.log("Setting up timer...");   
	const timerId = setInterval(() => {     
		setCount(prev => prev + 1);   
	}, 1000);    
	return () => {     
		console.log("Clearing timer...");     
		clearInterval(timerId);   
	}; 
}, []);
```

✅ Sets up timer on mount.  
✅ Cleans up on unmount (prevents memory leaks).

---

### c) Data Fetching Example

- State variables:
    - `data` → fetched data
    - `loading` → true/false
    - `error` → error details

`useEffect(() => {   const fetchData = async () => {     try {       const res = await fetch("https://api.example.com");       const json = await res.json();       setData(json);     } catch (err) {       setError(err);     } finally {       setLoading(false);     }   };   fetchData(); }, []);`

✅ Shows _“Loading…”_ until data fetched.  
✅ Handles errors gracefully.  
✅ Displays data when ready.

---

## 4️⃣ Rules of `useEffect`

- Must be called **inside a functional component** or **custom hook**.
    
- You can have **multiple `useEffect` hooks** in one component.
    
- **Dependency array** controls when effect runs.
    

---

## 🎯 Summary

✅ Lifecycle has **Mount → Update → Unmount**.  
✅ `useEffect` = one tool for handling all side effects.  
✅ Supports **cleanup** → avoids memory leaks.  
✅ Common use cases: **fetch data, timers, subscriptions, DOM changes**.