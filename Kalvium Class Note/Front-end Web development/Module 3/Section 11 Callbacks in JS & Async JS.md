# JavaScript – Callbacks & Asynchronous JS

## 🎯 Learning Goals

- Understand **asynchronous JavaScript** and why it's needed.
- Learn **callback functions** and how to use them.
- Use `setTimeout` to simulate asynchronous behavior.
- Explore real-world use cases: network requests, timers, event listeners.
- Understand **callback-based async code** execution flow.

---

## 🔹 1. What is Asynchronous JavaScript?

- JS is **single-threaded** → executes one task at a time.
- Asynchronous JS allows **long tasks** (like API calls, timers) to run **without blocking** the main thread.
- Analogy: Ordering food at a restaurant → you place the order (task), do other things, and the waiter (callback) brings it when ready.

---

## 🔹 2. What is a Callback Function?

- A **callback** is a function passed as an argument to another function and executed later.
- Allows code to **respond to events or completion of tasks**.

Example:

```js
function greetUser(name, callback) {   
	console.log("Hi, " + name);   
	callback(); 
}  
function showMessage() {   
	console.log("Welcome to the dashboard!"); 
}  
greetUser("Ravi", showMessage);
```

**Output:**

```
Hi, Ravi Welcome to the dashboard!
```

Explanation:

- `greetUser` accepts `showMessage` as a callback.
- After greeting, it executes the callback.

---

## 🔹 3. setTimeout: Simulating Async Behavior

- `setTimeout` schedules a task to run **after a delay**, without blocking code execution.

Example:

```js
console.log("Start");  
setTimeout(function() {   
	console.log("This runs after 2 seconds"); 
}, 2000);  
console.log("End");
```

**Output:**

```
Start End This runs after 2 seconds
```

Explanation: JS continues running while waiting for the timer.

---

## 🔹 4. Real-world Example: Simulating Data Loading

```js
function fetchData(callback) {   
	setTimeout(() => {     
		console.log("Data loaded!");     
		callback();   }, 3000); 
	}  
function showUI() {   
	console.log("Displaying UI..."); 
}  
fetchData(showUI);
```

Explanation:

- `fetchData` mimics an async operation (like fetching data from a server).
- `showUI` is called **after data is ready**.

---

## 🔹 5. When Are Callbacks Used?

- **User events:** clicking buttons, mouse events.
- **Timers:** `setTimeout`, `setInterval`.
- **API requests:** fetching data from server.
- **File reading, image loading, animations**.

**Purpose:** Keep app **responsive and non-blocking**.

---

## 🔹 6. Interactive Exercises

1. Log `"Step 1"` immediately, `"Step 2"` after 1 second, `"Step 3"` after 2 seconds.
2. Create `downloadFile(filename, callback)` → after 2 seconds, log `"Download complete"` and run the callback.
3. Simulate user login → delay `"Login successful"` and then call a callback to load the dashboard.

These exercises teach **timing, flow control, and async handling** using callbacks.

---

## 🔹 7. Key Takeaways

- **Asynchronous JS**: Handles long-running tasks without blocking the main thread.
- **Callbacks**: Functions passed to other functions to run later.
- Common async operations: **timers, API calls, events**.
- Callbacks **maintain responsiveness** in JS applications.

---

## 🔹 8. Useful Resources

- MDN – Callback Functions
- MDN – setTimeout
- JavaScript.info – Asynchronous JS

```embed
title: "Learn JavaScript CALLBACKS in 7 minutes! 🤙"
image: "https://i.ytimg.com/vi/i2SPq-nb3NQ/maxresdefault.jpg"
description: "00:00:00 introduction00:00:50 example 100:04:00 example 2// callback = a function that is passed as an argument//                    to another function.//  ..."
url: "https://youtu.be/i2SPq-nb3NQ"
favicon: ""
aspectRatio: "56.25"
```
