# JavaScript – Promises

## 🎯 Learning Objectives

- Understand what a **Promise** is and why it exists.
- Learn the **three states** of a Promise.
- Use **.then(), .catch(), and .finally()** to handle results.
- Rewrite callback-based async code using Promises.
- Simulate real-world async flows like **data fetching**.

---

## 🔹 1. What is a Promise?

- A **Promise** represents a value that may be available **now, in the future, or never**.
- It acts as a **placeholder for an async task**.
- Analogy: **Online order** → place order (async task), get product when fulfilled, or get error if rejected.

---

## 🔹 2. Promise States

1. **Pending** – Initial state, operation not complete.
2. **Fulfilled** – Operation completed successfully.
3. **Rejected** – Operation failed.

- `.then()` → handles **fulfilled** Promises.
- `.catch()` → handles **rejected** Promises.

---

## 🔹 3. Creating a Promise

```js
const myPromise = new Promise((resolve, reject) => {   
	const success = true;    
	setTimeout(() => {     
		if (success) {       
			resolve("Data fetched!");     
		} else {       
			reject("Failed to fetch data.");     
		}   
	}, 2000); 
});  
myPromise
	.then(result => console.log(result)) // "Data fetched!" 
	.catch(error => console.log(error)); // "Failed to fetch data."
```

**Explanation:**

- `resolve(data)` → called when async task succeeds.
- `reject(error)` → called when async task fails.
- `.then()` runs on **success**, `.catch()` runs on **failure**.

---

## 🔹 4. Real-world Example: Login Simulation

```js
function login(username, password) {   
	return new Promise((resolve, reject) => {     
		setTimeout(() => {       
			if (username === "admin" && password === "1234") { 
				resolve("Login successful!");       
			} else {         
				reject("Invalid credentials.");       
			}     
		}, 1500);   
	}); 
}  
login("admin", "1234")   
	.then(message => console.log(message)) // "Login successful!"
	.catch(err => console.log(err));
```

- Common in **API calls, form submissions, and file uploads**.
    

---

## 🔹 5. Using `.finally()`

```js
myPromise
.then(result => console.log(result))   
.catch(error => console.log(error))   
.finally(() => console.log("Promise completed"));
```

- `.finally()` runs **regardless of outcome**.
- Useful for **cleanup tasks** (e.g., hide loader).

---

## 🔹 6. Chaining Promises

- Avoids **callback hell** by chaining multiple async actions:

```js
getUser()   
.then(user => getPosts(user.id))   
.then(posts => displayPosts(posts))   
.catch(error => console.error("Error:", error));
```

- Each `.then()` returns a new Promise → smooth, readable flow.

---

## 🔹 7. Interactive Exercises

1. Create a Promise that **resolves with `"Loaded!"`** after 1 second.
2. Write `fetchData()` that **randomly resolves or rejects** and log the result.
3. Chain three `.then()` methods:
    - Simulate loading
    - Transform data
    - Log result

- Helps **replace nested callbacks** with clean async code.

---

## 🔹 8. Key Takeaways

- Promises handle **asynchronous operations** in a modern, readable way.
- States: **pending, fulfilled, rejected**.
- Use **.then()** for success, **.catch()** for errors, **.finally()** for cleanup.
- Promises **simplify async flows**, reduce nesting, and make debugging easier.

---

## 🔹 9. Useful Resources

- MDN – Promise
- JavaScript.info – Promises
- Eloquent JavaScript – Async Programming