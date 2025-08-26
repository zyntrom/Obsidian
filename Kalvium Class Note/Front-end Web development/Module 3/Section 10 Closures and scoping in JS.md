# JavaScript – Closures & Scope

## 🎯 Learning Goals

- Understand **scope** in JavaScript (global, function, block).
- Learn **closures** and how inner functions retain access to outer variables.
- Explore **lexical scoping** and its impact.
- Recognize potential **memory issues** with closures.
- Apply closures in **asynchronous programming**.

---

## 🔹 1. Scope in JavaScript

Scope defines **where variables are accessible**.

- **Global Scope**: Accessible anywhere.
- **Function Scope**: Accessible only within the function.
- **Block Scope**: Accessible only within `{}` if declared with `let` or `const`.

Example:

```js
let x = 'global';  
function test() {  
	let y = 'local';   
	console.log(x); // accessible   
	console.log(y); // accessible 
}  
console.log(x); // accessible 
console.log(y); // ReferenceError
```

---

## 🔹 2. Closures

A **closure** is a function that **remembers variables from its outer scope** even after the outer function has finished execution.

Example:

```js
function makeCounter() {   
	let count = 0;   
	return function() {     
		return count++; // retains access to count   
	}; 
}  
let counter = makeCounter(); 
console.log(counter()); // 0 
console.log(counter()); // 1 
console.log(counter()); // 2
```

✔ Inner function "closes over" the outer variables.

---

## 🔹 3. Lexical Scoping

- **Scope is determined where a function is defined**, not where it is called.
- Inner functions have access to variables from **outer functions**.

Example:

```js
function outer() {   
	let outerVar = 'I am outside!';      
	function inner() {     
		console.log(outerVar);   
	}      
	inner(); 
}  
outer(); // Logs: "I am outside!"
```

---

## 🔹 4. Closures and Memory

- Closures **retain variables**, which can lead to memory being kept alive longer than needed.
- Be cautious with **large objects or long-running applications**.

Example:

```js
function createCounter() {   
	let count = 0;   
	return function() {     
		return count++;   
	}; 
}  
let counter = createCounter(); // count stays in memory due to closure
```

---

## 🔹 5. Closures in Asynchronous Programming

- Useful for **callbacks, promises, and timers**.
- Retain state between async operations.

Example with `setTimeout`:

```js
function delayedMessage(message, delay) {   
	setTimeout(function() {     
		console.log(message);   
	}, delay); 
}  
delayedMessage("Hello, world!", 2000); // logs after 2 seconds

```
✔ The inner function keeps `message` and `delay` accessible even after the outer function finishes.

---

## 🔹 6. Exercise – Lexical Scoping

```js
function outer() {   
	let outerVar = 'I am outside!';      
	function inner() {     
		let innerVar = 'I am inside!';     
			console.log(outerVar); // ?     
			console.log(innerVar); // ?   
		}      
	inner(); 
}  
outer();
```

Questions:

1. Where is `outerVar` defined and accessible?
2. Where is `innerVar` defined and accessible?
3. What will be logged by `inner()`?

**Answers:**

- `outerVar` → defined in `outer()`, accessible inside `inner()` due to closure.
- `innerVar` → defined inside `inner()`, accessible only in `inner()`.
- Logs:

```
I am outside! I am inside!
```

---

## 🔹 7. Key Takeaways

- **Closures** allow inner functions to access outer function variables.
- **Lexical scoping** determines variable access based on **definition location**.
- Closures are **crucial in async JS** and **data privacy**.
- Watch out for **memory leaks** if closures hold large objects unnecessarily.

```embed
title: "Learn JavaScript Scoping In 10 Minutes"
image: "https://i.ytimg.com/vi/TkFN6e9ZDMw/maxresdefault.jpg"
description: "One of the biggest mistakes JavaScript developers make is not fully understanding how scoping works. There are 4 different levels of scoping and if you don’t..."
url: "https://youtu.be/TkFN6e9ZDMw"
favicon: ""
aspectRatio: "56.25"
```

---

## 🔹 8. Useful Resources

- [FreeCodeCamp – Closures in JavaScript](https://www.freecodecamp.org/news/closures-in-javascript-explained-with-examples/)
- [MDN – Closures](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures)
- [FreeCodeCamp – Lexical Scope](https://www.freecodecamp.org/news/javascript-lexical-scope-tutorial/)