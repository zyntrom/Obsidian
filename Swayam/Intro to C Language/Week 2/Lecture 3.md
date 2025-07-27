# 🔁 **C Programming: Computing GCD Using Loops**

---

## 🧮 **Problem Statement**

Compute the **Greatest Common Divisor (GCD)** of two **positive integers** `a` and `b`.

---

## 📘 **GCD Recursive Rule (Euclidean Algorithm)**

If:
- `b == 0` → `GCD(a, 0) = a`
- Else → `GCD(a, b) = GCD(b, a % b)`

---

## 🧾 **Program Overview**

- Input: Two positive integers from the user.
- If `a < b`, **swap them** to ensure `a ≥ b`.
- Apply the **Euclidean algorithm** using a `while` loop.

---

## 🛠️ **Step-by-Step Approach**

### 1. **Declare Variables**

```c
int a, b, t;
```

- `a`, `b`: inputs (and working values)
- `t`: temporary storage for swapping and preserving values

---

### 2. **Input Values**

```c
scanf("%d %d", &a, &b);
```

---

### 3. **Ensure a ≥ b**

Use **cyclic exchange** to swap if `a < b`.

#### 🔁 **Why we can’t do this:**

```c
a = b; 
b = a;
```

- Both variables will end up with the **same value** (original `b`).
- Original value of `a` is **lost**.

#### ✅ **Correct Swap Using Temp Variable**

```c
if (a < b) {     
	t = a;     
	a = b;     
	b = t; 
}
```

---

## 🧠 **Cyclic Swap: Real-World Analogy**

> Think of 2 nearly full rooms. To exchange their contents:
> - Move contents of Room A to a **third room** (temp).
> - Move Room B → Room A.
> - Move temp (Room A’s old contents) → Room B.

Same concept is used in **variable swapping**.

---

### 4. **Main GCD Loop**

```c
while (b != 0) {     
	t = a;        // store original a     
	a = b;        // a becomes b     
	b = t % b;    // b becomes old a % b 
}
```

---

### 5. **Output Result**

```c
printf("GCD is %d", a);
```

When `b == 0`, loop ends. At that point, `a` is the **GCD**.

---

## 🧪 **Execution Trace Example**

Input:

```c
a = 16, b = 9
```

|Iteration|a|b|t|b ≠ 0?|Comment|
|---|---|---|---|---|---|
|Start|16|9|-|Yes|Initial state|
|1|9|7|16|Yes|16 % 9 = 7|
|2|7|2|9|Yes|9 % 7 = 2|
|3|2|1|7|Yes|7 % 2 = 1|
|4|1|0|2|No|2 % 1 = 0 → loop ends|

Final result: `GCD = a = 1`

---

## 🔁 **Loop Invariant**

### 🔹 **Definition**:

A **loop invariant** is a **property that holds true** at the beginning of **every iteration** of the loop.

### 🧠 **Invariant in GCD Program**:

> Let `A` and `B` be the original inputs.  
> Let `a` and `b` be the loop variables.  
> Then, **`GCD(A, B) == GCD(a, b)`** throughout the loop.

### ✅ **Why It Matters**:

- Ensures the logic is correct.
- When the loop ends (`b == 0`), `a` is the **GCD(A, B)`.

---

## 🧮 **Why We Use Loop Invariants**

- Helps **prove correctness** of your code.
- Important in understanding loop behavior and debugging.
- Commonly tested in theoretical or MCQ-based questions.

---

## 📚 **Glossary**

|Term|Definition|
|---|---|
|GCD|Greatest number that divides both `a` and `b`|
|`%` (modulo)|Remainder after division|
|Loop Invariant|A condition that remains true throughout the loop|
|Cyclic Exchange|Technique to swap two variables using a third temporary variable|
|Sentinel Value|Special input that signals end of data (used in earlier session)|

---

## ✅ **Key Takeaways**

- Use `%` to compute remainders in GCD.
- Always **preserve original values** using temp variables when needed.
- Loop invariants help in both understanding and **verifying correctness**.
- A well-written `while` loop can efficiently solve mathematical problems.