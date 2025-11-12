## 🧠 Lesson 1.3 — Introduction to Proofs

---

### 🏁 Introduction

Have you ever noticed a pattern in math and thought,

> “This always works!”  
> But how do you _prove_ it always works — not just sometimes?

That’s where **proofs** come in.

A **proof** is a logical explanation that demonstrates why a statement is _always_ true — not based on examples or guesses, but on reasoning that works for **every possible case**.

---

### 🧩 What is a Proof?

> A **proof** is a logical, step-by-step argument that uses definitions, theorems, and logical reasoning to establish truth.

It ensures that results in math and computer science are **universally valid**, not just observed.

![[Pasted image 20251112143851.png]]
---

### 💡 Why Do Proofs Matter?

|Domain|Why Proofs Matter|
|---|---|
|**Mathematics**|Establish that a statement is always true for all possible cases|
|**Computer Science**|Prove that an algorithm is correct, a function behaves predictably, or a system is error-free|
|**Engineering & Physics**|Prevent errors in systems like bridges, rockets, or circuits|

Without proofs, we would rely only on testing or guessing — which is **not reliable** for systems that must always work.

---

## ⚙️ Types of Proof Methods

There are many methods to prove mathematical statements. The most common are:

1. **Direct Proof**
2. **Proof by Contradiction**
3. **Proof by Contrapositive**
4. **Proof by Cases**
5. (Later lessons) — _Proof by Induction_

---

## 🔹 1. Direct Proof

### 🧱 Definition

A **Direct Proof** shows that if the _premises_ (assumptions) are true, then the _conclusion_ logically follows.

### 🧭 Steps for Direct Proof

1. **Start with the Given:** State the assumptions (premises).
2. **Apply Logical Steps:** Use algebraic manipulation, definitions, or theorems.
3. **Reach the Conclusion:** Show that the result follows logically.

---

### ✳️ Example

**Statement:**  
If _m_ and _n_ are perfect squares, then _mn_ is also a perfect square.

**Proof:**  
Let

```
m = a²  and  n = b², where a, b ∈ ℤ
```

Then

```
mn = (a²)(b²) = (ab)²
```

Since _ab_ is an integer, _(ab)²_ is a perfect square. ✅  
Hence, _mn_ is a perfect square.

**Example with numbers:**  

```
m = 9 = 3², n = 16 = 4² → mn = 144 = 12² ✔
```

---

## 🔹 2. Proof by Contradiction

### 🧱 Definition

A **Proof by Contradiction** starts by assuming the _opposite_ of what you want to prove, and then showing that it leads to a **logical impossibility**.

### 🧭 Steps

1. **Assume the Opposite:** Suppose the statement is false.
2. **Derive a Contradiction:** Use logic or arithmetic to show an impossible situation.
3. **Conclude the Original Statement:** Since the assumption leads to contradiction, the statement must be true.

---

### ✳️ Example

**Statement:**  
If 3n + 2 is odd, then n is odd.

**Proof by Contradiction:**  
Assume 3n + 2 is odd, but n is even.  
Let n = 2m (since even).

```
3n + 2 = 3(2m) + 2 = 6m + 2 = 2(3m + 1)
```

This is **even**, which contradicts our assumption that 3n + 2 is odd. ❌  
Hence, n must be odd. ✅

---
```embed
title: "Methods of Proof"
image: "https://i.ytimg.com/vi/WXNKxMhj9pE/maxresdefault.jpg"
description: "This video was made with Clipchamp"
url: "https://youtu.be/WXNKxMhj9pE"
favicon: ""
aspectRatio: "56.25"
```

## 🔹 3. Proof by Contrapositive

### 🧱 Definition

Instead of proving

> “If P, then Q”  
> we prove its logically equivalent statement:  
> “If not Q, then not P” (¬Q → ¬P)

Because a statement and its contrapositive are always **logically equivalent**.

---

### 🧭 Steps

1. Identify contrapositive: “If not Q, then not P.”
2. Assume ¬Q (the negation of the conclusion).
3. Prove ¬P (the negation of the hypothesis).
4. Conclude that P → Q is true.

---

### ✳️ Example

**Statement:**  
If n² is odd, then n is odd.

**Contrapositive:**  
If n is even, then n² is even.

**Proof:**  
Let n = 2k (even).

```
n² = (2k)² = 4k² = 2(2k²)
```

Hence, n² is even. ✅  
Therefore, the contrapositive — and thus the original statement — is true.

---

## 🔹 4. Proof by Cases

### 🧱 Definition

Sometimes, a statement’s truth depends on **different cases** (e.g., whether a number is even or odd).  
We prove the statement separately for each case.

### 🧭 Steps

1. Split the statement into **all possible cases**.
2. Prove the statement is true in **each case**.
3. Conclude it is true for all cases.

---

### ✳️ Example

**Statement:**  
If n is an integer, then n² + 3n + 4 is even.

**Proof by Cases:**

**Case 1:** n is even → n = 2k

```
n² + 3n + 4 = (2k)² + 3(2k) + 4
             = 4k² + 6k + 4
             = 2(2k² + 3k + 2)

```

✅ Even

**Case 2:** n is odd → n = 2k + 1

```
n² + 3n + 4 = (2k + 1)² + 3(2k + 1) + 4
             = 4k² + 10k + 8
             = 2(2k² + 5k + 4)

```

✅ Even

Therefore, for both cases, n² + 3n + 4 is even. ✔

---

## 🧩 Practice Problems

### 🧮 1. Direct Proof

**Statement:** If m and n are odd integers, then m + n is even.

**Proof:**

```
m = 2a + 1, n = 2b + 1
m + n = 2a + 1 + 2b + 1 = 2(a + b + 1)
```

✅ Hence, m + n is even.

---

### 🔁 2. Proof by Contrapositive

**Statement:** If mn is even, then m is even or n is even.

**Proof:**  
Contrapositive: If m and n are both odd, then mn is odd.

```
m = 2a + 1, n = 2b + 1
mn = (2a + 1)(2b + 1) = 4ab + 2a + 2b + 1 = 2(2ab + a + b) + 1
```

✅ mn is odd, proving the contrapositive true.

---

### 🚫 3. Proof by Contradiction

**Statement:** If 5x + 25y = 1723, then x or y is not an integer.

**Proof:**  
Assume x and y are integers.

```
5(x + 5y) = 1723
```

Then 1723 must be divisible by 5. But 1723 ÷ 5 = 344.6 ❌ (not integer).  
Contradiction!  
✅ Hence, x or y is not an integer.

---

### 🧭 4. Proof by Cases

**Statement:** If (x² − 1)/(x + 2) > 0, then x > 1 or −2 < x < −1.

**Proof Summary:**  
Factor numerator: (x + 1)(x − 1)/(x + 2) > 0  
Test combinations of signs of (x + 1), (x − 1), (x + 2):

✅ Case 1: All positive → x > 1  
✅ Case 4: Two negative, one positive → −2 < x < −1

Hence, result holds for either x > 1 or −2 < x < −1.

---

## 🧠 Summary

|Method|Idea|Example Statement|
|---|---|---|
|**Direct Proof**|Use logic from premise to conclusion|If n is even → n² is even|
|**Proof by Contradiction**|Assume the opposite; find a contradiction|If 3n + 2 is odd → n is odd|
|**Proof by Contrapositive**|Prove “If not Q → not P” instead of “If P → Q”|If n² is odd → n is odd|
|**Proof by Cases**|Split into separate conditions|If n is integer → n² + 3n + 4 is even|

---

### 🧩 Where Proofs Are Used

|Field|Example|
|---|---|
|**Math & Logic**|Theorems, number properties|
|**Computer Science**|Algorithm correctness, program verification|
|**Engineering**|System safety and stability proofs|
|**Cryptography**|Proving encryption and security soundness|

---

## 📚 Bonus Resources

- How to Write Mathematical Proofs – Hamilton
- [Proofs and Types of Proofs – Medium](https://medium.com)
- [Introduction to Mathematical Proofs – GeeksforGeeks](https://www.geeksforgeeks.org)
- [Types of Proof – YouTube](https://www.youtube.com)

![[Pasted image 20251112143921.png]]