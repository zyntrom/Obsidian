# JavaScript – Recursive Functions

## 🎯 Learning Objectives

- Understand **what recursion is** and how it works
- Learn the **two parts** of recursion: base case + recursive case
- Write recursive functions for simple problems
- Recognize when recursion is useful (and when not)
- Compare recursion vs iteration

---

## 🔹 1. What is Recursion?

- **Recursion** = when a function **calls itself** to solve smaller subproblems.
- Works like **Russian nesting dolls** → keeps breaking problem into smaller parts until the **base case** is reached.

---

## 🔹 2. Parts of a Recursive Function

1. **Base Case** → stopping condition (prevents infinite loop).
2. **Recursive Case** → function calling itself with smaller input.

---

## 🔹 3. Example – Factorial (n!)

```js
function factorial(n) {   
	if (n === 0) {     
		return 1; // Base case   
	} else {     
		return n * factorial(n - 1); // Recursive case   
	} 
}  
console.log(factorial(5)); // 120
```

✔ Keeps calling until `n === 0`.  
✔ Then returns results back step by step.

---

## 🔹 4. Example – Countdown

```js
function countdown(n) {   
	if (n === 0) {     
		console.log("Liftoff!");   
	} 
	else {     console.log(n);     countdown(n - 1);   } }  countdown(5);
```

Output:

`5   4   3   2   1   Liftoff!`  

✔ Each call prints number, then recurses with `n - 1`.

---

## 🔹 5. When to Use Recursion

✅ Good for problems that **repeat in smaller versions**:

- Factorial, Fibonacci numbers
    
- Tree traversal (DOM, file systems)
    
- Searching nested data (arrays/objects)
    

---

## 🔹 6. Be Careful → Infinite Recursion ⚠️

Every recursive function **must have a base case**.  
Otherwise → **stack overflow error**.

`function endless() {   return endless(); // ❌ No base case → infinite loop }`

---

## 🔹 7. Recursive vs Iterative

- **Iteration** (loops) → may be faster, uses less memory.
    
- **Recursion** → cleaner, matches problem structure (especially with nested/branching data).
    

---

## 🔹 8. Real-World Example – Sum of Nested Array

`function sumNestedArray(arr) {   let sum = 0;   arr.forEach(element => {     if (Array.isArray(element)) {       sum += sumNestedArray(element); // Recursive call     } else {       sum += element;     }   });   return sum; }  console.log(sumNestedArray([1, [2, [3, 4]], 5])); // 15`

✔ Keeps going deeper into nested arrays until all numbers are added.

---

## 🔹 9. Practice Exercises

1. Recursive function to calculate **sum from 1 to n**
    
2. Recursive function to **reverse a string**
    
3. Recursive function to **print all elements of a nested object**
    

---

## 📝 Summary

- Recursion = function calling itself.
    
- Needs **Base Case** (stop) + **Recursive Case** (repeat).
    
- Useful for **nested or tree-like problems**.
    
- Watch out for **infinite recursion** (stack overflow).
    
- Can replace loops, but not always memory-efficient.