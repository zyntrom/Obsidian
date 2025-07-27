# 🧮 Lecture Notes: Computing the GCD (Greatest Common Divisor)

---

## 📌 Objective

To understand and implement an efficient algorithm to compute the **GCD** (or **HCF**) of two positive integers `m` and `n`.

---

## 📚 Concepts Introduced

### 🔢 What is the GCD?

- **GCD (Greatest Common Divisor)**: The largest positive integer that divides both `m` and `n` without leaving a remainder.
- Also known as **HCF (Highest Common Factor)**.

---

## ❗ Naive Algorithm for GCD

### 🔍 Description:

1. Take the **smaller of the two numbers**, say `n`.
2. Loop down from `k = n` to `1`.
3. For each `k`, check if `k` divides both `m` and `n`.
4. The first such `k` is the **GCD**.

### 🛑 Problem:

- **Very slow** for large numbers.
- If `m` and `n` are **relatively prime**, the GCD is `1`, and we may need to check all the way down to `1`.

---

## ⚡ Euclid’s Algorithm (Efficient Approach)

### 🧠 Intuition:

- If a number `d` divides both `a` and `b`, then it must also divide `a % b`.
- Thus, the GCD of two numbers doesn't change if we **replace the larger number with the remainder**.

### 📏 Rod Analogy:

- Visualize `a = 8`, `b = 6` as two rods.
- Try to divide the longer rod with the shorter.
- Remainder = 2.
- Now divide `6` with `2` → No remainder.
- Hence, `2` is the GCD.

---

## 🔁 Euclid’s Algorithm (Iterative Version)

### 💡 Key Idea:

> **GCD(a, b) = GCD(b, a % b)**  
> Repeat until `b == 0`. Then, `a` is the GCD.

### 🧮 Step-by-Step Example:

**Input**: `a = 102`, `b = 21`

1. `102 % 21 = 18` → GCD(21, 18)
2. `21 % 18 = 3` → GCD(18, 3)
3. `18 % 3 = 0` → STOP
4. **GCD = 3**

---

## 🧑‍💻 Algorithm in Pseudocode

```
Input: Two positive integers a and b  
// Ensure a ≥ b If a < b:     
	Swap a and b  
While b ≠ 0:     
	g = a % b      // Take remainder     
	a = b          // Shift values     
	b = g  
Output: a is the GCD
```

---

## 🔃 Step-by-Step Dry Run

**Example**: Find GCD(8, 6)

|Step|a|b|g = a % b|Comment|
|---|---|---|---|---|
|Init|8|6|||
|1|8|6|2|8 % 6 = 2|
|2|6|2|0|6 % 2 = 0|
|3|2|0||Stop → GCD = 2|

---

## 🧰 Key Programming Concepts Introduced

### 📦 Variables

- **a, b, g**: Used to store intermediate values.
- Think of variables as **boxes** holding current values.

### ➡️ Assignment Operator (=)

- `a = b` means: Copy the value of `b` into `a`.

### 📋 Sequential Execution

- Multiple statements like:
```
    g = a % b; 
    a = b; 
    b = g;
```
    
    are executed **in order**, one after another.

---

## 📝 Notes on Swapping Two Variables

To ensure `a ≥ b`, you might need to **swap** values:

```
temp = a; 
a = b; 
b = temp;
```

This uses a **temporary variable** to hold a value during the swap.

---

## ✅ Summary

|Topic|Key Points|
|---|---|
|**GCD**|Largest number dividing both `a` and `b` without remainder|
|**Naive GCD**|Try every `k` from min(a, b) down to 1|
|**Euclid’s Algorithm**|Repeated modulo → GCD(a, b) = GCD(b, a % b)|
|**Efficiency**|Much faster than naive method|
|**Implemented via loop**|Stops when `b == 0`|
|**Modulo operator `%`**|Gives remainder after division|
|**Variables & assignment**|Fundamental to algorithm implementation|

---

## 📌 Equation to Remember

GCD(a,b)=GCD(b,a%b)\text{GCD}(a, b) = \text{GCD}(b, a \% b)GCD(a,b)=GCD(b,a%b)