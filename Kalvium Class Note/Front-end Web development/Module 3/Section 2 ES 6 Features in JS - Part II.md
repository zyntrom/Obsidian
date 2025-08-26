# ES6 Features in JavaScript – Part II

## 1. Default Parameters

- Allows functions to have **default values** for arguments if not provided.

Example:

```js
function greet(name = "friend", greeting = "Hi") {
	console.log(`${greeting}, ${name}!`); 
}  
greet();               // "Hi, friend!" 
greet("Alice");        // "Hi, Alice!" 
greet("Bob", "Hello"); // "Hello, Bob!"
```

✅ **Why useful?** → Avoids errors from missing arguments and keeps functions cleaner.
```embed
title: "ES6 Default Parameters: A Beginner's Guide to Mastering JavaScript from Zero to Hero"
image: "https://i.ytimg.com/vi/MHyp9Gi7Gpw/maxresdefault.jpg"
description: "ES6 Default Parameters: A Beginner's Guide to Mastering JavaScript from Zero to HeroEver wanted to make your JavaScript functions more flexible? In this vide..."
url: "https://youtu.be/MHyp9Gi7Gpw"
favicon: ""
aspectRatio: "56.25"
```


---

## 2. Spread & Rest Operators (`...`)

### Spread Operator → expands arrays/objects

```js
let numbers = [1, 2, 3]; 
let moreNumbers = [4, 5, 6]; 
let allNumbers = [...numbers, ...moreNumbers];  
console.log(allNumbers); // [1, 2, 3, 4, 5, 6]
```

### Rest Operator → collects multiple arguments into an array

```js
function sum(...numbers) {   
	return numbers.reduce((total, num) => total + num, 0); 
}  
console.log(sum(1, 2, 3));       // 6 
console.log(sum(4, 5, 6, 7));    // 22
```

✅ **Why useful?** →

- Spread → combine/copy arrays or objects easily.
- Rest → handle unlimited function arguments.

---

## 3. Classes

- Cleaner, OOP-style syntax for creating objects and methods.

Example:

```js
class Person {   
	constructor(name, age) {     
		this.name = name;     
		this.age = age;   
	}    
	introduce() {     
		console.log(`Hi, I’m ${this.name}, and I’m ${this.age} years old.`);   
	} 
}  
let alice = new Person("Alice", 25); 
alice.introduce(); // "Hi, I’m Alice, and I’m 25 years old."
```

✅ **Why useful?** → Organizes code, improves reusability and readability.

---

## 4. Maps and Sets

### Map → key-value pairs

```js
let userMap = new Map(); 
userMap.set("name", "Alice"); 
userMap.set("age", 25);  
console.log(userMap.get("name")); // "Alice" 
console.log(userMap.size);        // 2
```

### Set → stores unique values

```js
let numbers = new Set([1, 2, 2, 3]); 
console.log(numbers.size); // 3 
console.log(numbers.has(2)); // true
```

✅ **Why useful?** →

- Maps = better than objects for dynamic key-value data.
- Sets = automatic duplicate removal, efficient lookups.

---

## 5. Modules

- Split code into multiple files for better maintainability.
```embed
title: "ES6 Rest & Spread operators"
image: "https://i.ytimg.com/vi/QtGbcvZ6774/maxresdefault.jpg"
description: "The Rest and Spread operators are two sides of the same thing - the ability to take an array and break it apart into its individual components or combine a b..."
url: "https://youtu.be/QtGbcvZ6774"
favicon: ""
aspectRatio: "56.25"
```

**Export (math.js):**

```js
export function add(a, b) {   
	return a + b; 
}
```

**Import (main.js):**

```js
import { add } from './math.js';  console.log(add(2, 3)); // 5
```

✅ **Why useful?** → Code reuse, cleaner project structure.

---

## 6. Key Takeaways

- **Default parameters** → safer functions with fallback values.
- **Spread/Rest (`...`)** → powerful syntax for arrays, objects, and arguments.
- **Classes** → OOP-style, structured code.
- **Maps & Sets** → efficient data storage with unique benefits.
- **Modules** → reusable, maintainable, and scalable code organization.