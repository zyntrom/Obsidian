# Pure and Impure Functions in JavaScript

## 🎯 Learning Goals

- Define Pure Functions
- Spot Impure Functions
- Checklist for purity:
    - Same inputs = Same outputs
    - No side effects
- Why Pure Functions matter
- Role of Impure Functions

---

## 🔹 What is a Pure Function?

- A **pure function** always produces the **same output** for the **same input**.
- It **does not modify global state** or cause side effects.

Example:

```js
function add(x, y) {   
	return x + y; 
}  
console.log(add(2, 3)); // 5 
console.log(add(2, 3)); // 5 (consistent)
```

✅ Characteristics:

- Same input → same output
- No global tampering
- No console logs, DOM changes, alerts, DB updates

---

## 🔹 What is an Impure Function?

- Functions that **modify external state** or **produce side effects**.
- Output is **not predictable** only from inputs.

### Example 1: Modifying Global State

```js
let counter = 0;  
function incrementCounter() {   
	counter++; // touches external state → impure 
}
```

### Example 2: Randomness / Logging

```js
function logMessage(msg) {   
	console.log(msg); // side effect 
}  
function rollDice() {   
	return Math.ceil(Math.random() * 6); // unpredictable output 
}

```
---

## 🔹 Why Are Pure Functions Awesome?

- ✅ Predictable → Same input = same output
- ✅ Easy to test → No hidden dependencies
- ✅ Debugging-friendly → Fewer mystery bugs
- ✅ Reusable → Can move across projects easily
- ✅ Functional programming friendly

---

## 💥 Are Impure Functions Always Bad?

- ❌ No — they are necessary for real-world tasks.
- Examples:
    - Saving to a database
    - Logging errors
    - Updating UI / DOM

👉 **Best practice:**

- Use **pure functions** for logic and data transformations.
- Keep **impure functions** isolated (API calls, I/O).

```embed
title: "Pure Functions / Intro to JavaScript ES6 programming, lesson 17"
image: "https://i.ytimg.com/vi/dZ41D6LDSBg/maxresdefault.jpg"
description: "Learn about determinism, side effects, and  pure functions.👉 Watch this to learn about abstraction https://www.youtube.com/watch?v=_y-5nZAbgt4📩 Subscribe t..."
url: "https://youtu.be/dZ41D6LDSBg"
favicon: ""
aspectRatio: "56.25"
```

```embed
title: "Learn Pure Functions In 10 Minutes"
image: "https://i.ytimg.com/vi/fYbhD_KMCOg/maxresdefault.jpg"
description: "Functional programming is constantly on the rise, and with functional programming comes pure functions. Pure functions are the base of what functional progra..."
url: "https://youtu.be/fYbhD_KMCOg"
favicon: ""
aspectRatio: "56.25"
```

---

## 🔹 Quick Checklist

|Criteria|Pure Function ✅|Impure Function ❌|
|---|---|---|
|Same input → same output|Yes|Not guaranteed|
|Modifies global variables|No|Might|
|Has side effects (logging, DOM)|No|Often|
|Easy to test|Yes|Sometimes|

---

## 🧼 Analogy: Dishwasher

- **Pure function** = Dishwasher → Input dirty dishes → Output clean dishes (always predictable).
- **Impure function** = Dishwasher throwing forks at you → unpredictable and chaotic.

---

## 🎉 Wrap-up

- Pure functions = reliable, testable, predictable code.
- Impure functions = necessary for real-world interaction but should be minimized/isolated.
- Balance = Pure for logic, Impure for external communication.