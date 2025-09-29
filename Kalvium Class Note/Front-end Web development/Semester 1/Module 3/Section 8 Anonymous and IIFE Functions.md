# JavaScript – Anonymous Functions & IIFEs

## 🎯 Learning Goals

- Understand **Anonymous Functions**
- Learn **Arrow Functions** as shorthand
- Explore **IIFE (Immediately Invoked Function Expressions)**
- Use IIFE with **parameters**
- Use IIFE for **private scope / avoiding conflicts**

---

## 🔹 1. Anonymous Function – _“More than just a name”_

- A function **without a name**.
- Used for **short, specific tasks** → often as arguments to other functions.
- Once done, it’s not reused.

Example:

```js
let numbers = [1, 2, 3, 4, 5]; 
numbers.forEach(function(number) {     
	console.log(number); 
});
```

Output:

```
1 2 3 4 5
```

✔ Temporary function used only to print numbers.

---

## 🔹 2. Arrow Function – _“A streamlined tool”_

- Shorter syntax for anonymous functions.
- More concise, often used for inline functions.

Example:

```js
let multiply = (a, b) => a * b; 
console.log(multiply(2, 3)); // 6
```

✔ => is shorthand for function definition.  
✔ Great for callbacks & small functions.

---

## 🔹 3. IIFE – _“The function that doesn’t wait”_

- **Immediately Invoked Function Expression**.
- Runs **immediately after definition**.
- No need to call it separately.

Example:

```js
(function() {   
	console.log("Hello, IIFE!"); 
})();
```

Output:

```
Hello, IIFE!
```

✔ Acts like a one-time-use machine.

---

## 🔹 4. IIFE with Parameters

- You can **pass arguments** directly.

Example:

```js
(function(name) {   
	console.log("Hello, " + name + "!"); 
})("John");
```

Output:

```
Hello, John!
```

---

## 🔹 5. IIFE for Private Scope – _“Keeping things organized”_

- Variables inside an IIFE **don’t leak** into global scope.
- Helps avoid conflicts with other variables.

Example:

```js
var global = "I am global";  
(function() {   
	var global = "I am private";   
	console.log(global); // I am private 
})();  
console.log(global); // I am global
```

✔ Inside IIFE → private variable  
✔ Outside → global variable untouched

---

## 🔹 6. Practice – Build Your Own IIFEs

- Create IIFEs that:
    - Add two numbers
    - Reverse a string
    - Return today’s date

Example:

```js
let today = (function() {   
	return new Date().toDateString(); 
})(); 
console.log(today); 
```

---

## 📝 Wrap-up

- **Anonymous Function** → unnamed, short task
- **Arrow Function** → shorter syntax, efficient for inline use
- **IIFE** → executes instantly after definition
- **IIFE with parameters** → can accept input on the spot
- **Private scope** → avoids global namespace pollution