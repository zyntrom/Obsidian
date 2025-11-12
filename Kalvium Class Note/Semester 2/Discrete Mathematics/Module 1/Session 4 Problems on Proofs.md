## 🧠 Kalvium — AL

### 🧩 1.4 Problems on Proofs

---

### 📝 Overview

This is an **optional, assignment-based lesson** designed to help you **practice different methods of proof**. Working through these problems will strengthen your logical reasoning and deepen your understanding of mathematical proofs.

---

### 🔍 Practice Questions

---

#### **1️⃣ Direct Proof**

**Statement:** Prove that the sum of two even integers is even.

**Proof:**  
Let the two even integers be:  
m = 2a and n = 2b, where _a_ and _b_ are integers.

Then,  

```
m + n = 2a + 2b = 2(a + b)
```

Since _(a + b)_ is an integer, _m + n_ is of the form 2 × integer.

✅ **Therefore, the sum of two even integers is even.**

---

#### **2️⃣ Proof by Contradiction**

**Statement:** Prove that √2 is irrational.

**Proof:**  
Assume, for contradiction, that √2 is rational.  
Then it can be written as **p/q**, where _p_ and _q_ are integers with no common factors.

```
√2 = p/q  
⇒ 2 = p²/q²  
⇒ p² = 2q²
```
This implies _p²_ is even, so _p_ must be even. Let _p = 2k_.

```
Substituting:  
(2k)² = 2q²  
⇒ 4k² = 2q²  
⇒ q² = 2k²
```

Hence, _q_ is also even.  
This contradicts the assumption that _p_ and _q_ have no common factors.

✅ **Therefore, √2 is irrational.**

---

#### **3️⃣ Proof by Contrapositive**

**Statement:** If n² is even, then n is even.

**Contrapositive:** If n is odd, then n² is odd.

**Proof:**  
Let n = 2k + 1, where _k_ is an integer.

```
Then,  
n² = (2k + 1)²  
= 4k² + 4k + 1  
= 2(2k² + 2k) + 1
```

This is of the form 2m + 1 → odd.

✅ **Hence, by contrapositive reasoning, if n² is even, then n is even.**

---

#### **4️⃣ Proof by Cases**

**Statement:** Prove that |x| = x if x ≥ 0, and |x| = −x if x < 0.

**Proof:**

**Case 1:** If x ≥ 0  
Then, by the definition of absolute value, |x| = x.

**Case 2:** If x < 0  
Then, |x| = −x (since −x is positive when x is negative).

✅ **Therefore, |x| = x if x ≥ 0 and |x| = −x if x < 0.**

---

#### **5️⃣ Proof by Contradiction**

**Statement:** Prove that there is no smallest positive rational number.

**Proof:**  
Assume there exists a smallest positive rational number, call it _r_.

But then, _r/2_ is also positive and smaller than _r_.  
This contradicts our assumption that _r_ is the smallest.

✅ **Hence, no smallest positive rational number exists.**

---

### 💡 Summary

- This lesson reinforces your understanding of **proof techniques** through practice.
- Covered proof types:
    - **Direct Proof** — show the conclusion logically follows.
    - **Contradiction** — assume the opposite, derive a contradiction.
    - **Contrapositive** — prove the logically equivalent negation.
    - **Proof by Cases** — handle all possible scenarios separately.

---

### 🧭 Takeaway

Proofs form the **foundation of logical reasoning** in mathematics and computer science.  
Practice problems like these build precision, structure, and clarity in problem-solving.