## 📘 JavaScript Functions – Quick Notes

### 🧠 What is a Function?

- A **function** is a block of code to perform a specific task.
- Makes code **modular**, **reusable**, and **organized**.
- Like a **recipe**: use it repeatedly with different ingredients (inputs).

---

### ✅ Why Use Functions?

- **Reusability** – Write once, use many times.
- **Organization** – Break complex tasks into steps.
- **Readability** – Cleaner and understandable code.

---

### ✍️ Declaring a Function

```js
function greet(name) {   
	console.log("Hello, " + name + "!"); 
}
```

- `function`: keyword
- `greet`: name of the function
- `(name)`: parameter (like an input placeholder)
- `{ ... }`: function body (code to run)

---

### 📞 Calling a Function

```js
greet("Kalvian"); // Output: Hello, Kalvian! 
greet("Student"); // Output: Hello, Student!
```

- Call a function using its name + `()`
- Pass **arguments** into it (`"Kalvian"`, `"Student"`)

---

### ⚙️ Parameters vs. Arguments

```js
function add(a, b) {   
	return a + b; 
}  
let sum = add(5, 3); // 8
```

- **Parameters**: placeholders (`a`, `b`)
- **Arguments**: real values (`5`, `3`)

---

### 🔁 Returning Values

```js
function multiply(x, y) {   
	return x * y; 
}  
let product = multiply(4, 6); // 24
```

- `return` gives back a result
- If no `return`, the function returns `undefined`

---

### 🧪 Function Expression

```js
let square = function(number) {   
	return number * number; 
};  
let result = square(5); // 25
```

- Store functions in variables
- Useful for dynamic or conditional usage

---

### 🧾 Summary

- **Functions** = reusable code blocks
- Declared with `function` keyword
- Called with `()`
- Use **parameters** for inputs, **return** for outputs
- Can be written as **expressions** too