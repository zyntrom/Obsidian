# ES6 Features in JavaScript – Part I

## 1. Why ES6 Matters

- Released in **2015**, ES6 (ECMAScript 2015) was a **major upgrade** to JavaScript.
- Fixed issues with **var** (scope leakage).
- Introduced **clearer syntax, better readability, scalability, and bug reduction**.
- ES6 features are **standard in modern web development**.

---

## 2. `let` & `const`

### Problem with `var`

- Function-scoped, not block-scoped.
- Variables declared with `var` leak outside `{}` blocks.

Example:

```js
function testVar() {   
	if (true) {     
		var name = "Alice";   
	}   
	console.log(name); // Accessible (bad!) 
}
```

### Solution → `let` and `const`

- **`let`** → block-scoped, re-assignable.
- **`const`** → block-scoped, cannot be reassigned (but object properties can still change).

Example:

```js
{   
	let greeting = "hello";   
	console.log(greeting); // "hello" 
} 
console.log(greeting); // ReferenceError  
const PI = 3.14; 
PI = 3.14159; // TypeError
```

⚠️ **Note:** `const` does **not** make objects immutable.

```js
const person = { name: "Sam" }; 
person.name = "Sara"; // Allowed
```

---

## 3. Arrow Functions

- Provide **shorter syntax**.
- Automatically **bind `this`** (no manual `.bind()` needed).
- Great for callbacks and array methods.

Example:

```js
let numbers = [1, 2, 3]; 
let doubled = numbers.map(n => n * 2); 
console.log(doubled); // [2, 4, 6]
```

Mini Challenge:

```js
// Traditional 
function greet(name) {   
	return "Hello, " + name; 
}  // ES6 Arrow Function 
let greet = name => `Hello, ${name}`;
```

---

## 4. Template Literals

- Use **backticks `` ` ``** instead of quotes.
- Support **multi-line strings** and **string interpolation** using `${}`.

Example:

```js
let user = "John"; 
let age = 30; 
console.log(`Hi, I’m ${user} and I’m ${age} years old.`);
```

Challenge:

``let city = "Chennai"; let temp = 32; console.log(`The temperature in ${city} is ${temp}°C.`);``

---

## 5. Destructuring

- Extract values from **objects** and **arrays** easily.
    

### Object Destructuring

`const user = { name: "Alice", age: 22 }; const { name, age } = user; console.log(name); // "Alice"`

### Array Destructuring

`const arr = [10, 20]; const [a, b] = arr; console.log(a, b); // 10 20`

---

## 6. Key Benefits of ES6 Features

- **let/const** → safer variable declarations.
    
- **Arrow functions** → cleaner functions, better `this` handling.
    
- **Template literals** → more readable string formatting.
    
- **Destructuring** → concise data extraction from arrays/objects.