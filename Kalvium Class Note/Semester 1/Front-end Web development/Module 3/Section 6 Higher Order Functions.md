# JavaScript – Higher Order Functions (HOFs)

## 🎯 Learning Objectives

- Understand what makes a function **higher-order**
- Learn to **pass functions as arguments**
- Learn to **return functions from functions**
- Recognize built-in **map, filter, reduce**
- Practice building **your own HOFs**

---

## 🔹 1. What is a Higher-Order Function?

A **Higher-Order Function (HOF)** is a function that does at least one of the following:

1. **Takes another function** as an argument (callback).
2. **Returns a new function** as a result.

👉 Think of it as **functions managing functions**.

---

## 🔹 2. Passing Functions as Arguments

**Example:**

```js
function greet(name) {   
	return "Hello, " + name; 
}  
function processUserInput(callback) {   
	const name = "Aditi";   
	return callback(name); 
}  
console.log(processUserInput(greet));  // Output: "Hello, Aditi"

```
✔ `processUserInput` is an HOF because it accepts another function (`greet`).  
✔ Useful for **customizable behavior**.

---

## 🔹 3. Returning Functions from Functions

**Example:**

```js
function multiplier(factor) {   
	return function(number) {     
		return number * factor;   
	}; 
}  
const double = multiplier(2); 
console.log(double(5)); // 10
```

✔ `multiplier` returns a **new function**.  
✔ Creates **function factories** (like `double`, `triple`).

---

## 🔹 4. Built-in Higher-Order Functions in JS

Commonly used HOFs in **arrays**:

- **map()** → transforms each element

```js
const numbers = [1, 2, 3, 4, 5]; 
const squared = numbers.map(num => num * num); 
console.log(squared); // [1, 4, 9, 16, 25]
```

- **filter()** → keeps elements that satisfy condition

```js
const evens = numbers.filter(num => num % 2 === 0); 
console.log(evens); // [2, 4]
```

- **reduce()** → combines all into single result

```js
const sum = numbers.reduce((acc, num) => acc + num, 0); 
console.log(sum); // 15
```

---

## 🔹 5. Real-World Example → Reusable Logging

```js
function withLogging(fn) {   
	return function(...args) {     
		console.log("Calling function...");     
		const result = fn(...args);     
		console.log("Result:", result);     
		return result;   
	}; 
}  
function add(a, b) {   
	return a + b; 
}  
const loggedAdd = withLogging(add); 
loggedAdd(3, 4); // Logs: Calling function... | Result: 7
```

✔ `withLogging` is an HOF that **enhances behavior** without modifying the original function.

---

## 🔹 6. Interactive Exercises

1. **Repeat a function n times**

```js
function repeat(fn, n) {   
	for (let i = 0; i < n; i++) 
	fn(); 
}
```

2. **Make greeting factory**

```js
function makeGreeting(greeting) {   
	return function(name) {     
		return `${greeting}, ${name}!`;   
	}; 
}
```

3. **Apply function twice**

```js
function applyTwice(fn, value) {   
	return fn(fn(value)); 
}
```

---

## 📝 Summary

- **HOFs** → functions that take/return other functions.
- Allow **flexible, reusable, and clean design**.
- Built-in HOFs → `map`, `filter`, `reduce`.
- Can build your own → decorators, callbacks, function factories.
- Helps in **thinking functionally** → more expressive code.

```embed
title: "Higher Order Function | javascript interview series"
image: "https://i.ytimg.com/vi/E7WIis2NjZU/maxresdefault.jpg"
description: "Welcome to a youtube channel dedicated to programming and coding related tutorials. We talk about tech, write code, discuss about cloud and devops. That’s wh..."
url: "https://youtu.be/E7WIis2NjZU"
favicon: ""
aspectRatio: "56.25"
```
