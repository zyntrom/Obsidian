## 🌀 JavaScript Loops — Quick Notes

### 📌 What Are Loops?

Loops allow you to **repeat a block of code** multiple times, making your program shorter, smarter, and more efficient.

---

### 🔁 Types of Loops

#### 1. **`for` loop**

Use when you **know** how many times to repeat.

**Syntax:**

```js
for (let i = 1; i <= 5; i++) {   
	console.log("Iteration number: " + i); 
}
```

- Starts with: `let i = 1` (initialization)
- Runs while: `i <= 5` (condition)
- Increases i: `i++` (increment)

✅ Best when: You know the number of repetitions.

---

#### 2. **`while` loop**

Use when you **don’t know** in advance how many times to repeat.

**Syntax:**

```js
let i = 1; 
while (i <= 5) {   
	console.log("Iteration number: " + i);   
	i++; 
}
```

✅ Best when: You loop **as long as a condition is true**.

---

#### 3. **`do...while` loop**

Use when you want to **guarantee at least one run**, even if the condition is false.

**Syntax:**

```js
let i = 6; 
do {   
	console.log("Iteration number: " + i);   
	i++; 
} while (i <= 5);
```

✅ Best when: You **must run** the loop body **at least once**.

---

### 💡 Summary:

|Loop Type|When to Use|Runs at least once?|
|---|---|---|
|`for`|Known number of iterations|No|
|`while`|Unknown number, depends on condition|No|
|`do...while`|Must run once before checking condition|✅ Yes|

---

### 🧠 Real-Life Examples:

- **`for`**: Print 1 to 100
- **`while`**: Keep asking user input until it's valid
- **`do...while`**: Show welcome message at least once