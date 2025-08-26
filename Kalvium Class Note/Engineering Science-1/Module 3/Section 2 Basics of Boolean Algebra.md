# Basics of Boolean Algebra

## 1. Boolean Variables

- Boolean variable → has only **two states**:
    - 1 (True / ON)
    - 0 (False / OFF)
- Analogy:
    - A **light switch** → ON (1) or OFF (0).
- Importance:
    - Foundation of all **digital computations**.
    - Used to represent information in binary.
    - Combine multiple Boolean variables → form **logic expressions**.

---

## 2. Basic Boolean Operations

### a) AND (•, ∧)

- Output = 1 only if **all inputs are 1**.
- Analogy: A club that admits you **only if all rules are satisfied**.
- Example: A • B

|A|B|A • B|
|---|---|---|
|0|0|0|
|0|1|0|
|1|0|0|
|1|1|1|
![[Pasted image 20250826095216.png]]
---

### b) OR (+, ∨)

- Output = 1 if **at least one input is 1**.
- Analogy: A restaurant gives a discount if you order **burger OR pizza**.
- Example: A + B

| A   | B   | A + B |
| --- | --- | ----- |
| 0   | 0   | 0     |
| 0   | 1   | 1     |
| 1   | 0   | 1     |
| 1   | 1   | 1     |
![[Pasted image 20250826095228.png]]
---

### c) NOT (¬, ′, overbar)

- Inverts input:
    - 0 → 1
    - 1 → 0
- Analogy: A reverse switch that flips the state.
- Example: A′

| A   | A′  |
| --- | --- |
| 0   | 1   |
| 1   | 0   |
![[Pasted image 20250826095254.png]]
---

## 3. Boolean Expressions & Truth Tables

- Combine variables with operations → Boolean expression.
- Example: (A • B) + (C′)
- Truth Table shows output for **all input combinations**.
- Helps to:
    - **Analyze circuits**.
    - **Verify correctness** of design.
![[Pasted image 20250826095307.png]]
---

## 4. Fundamental Laws of Boolean Algebra

1. **Identity Law**
    - A + 0 = A
    - A • 1 = A
2. **Null (Absorption) Law**
    - A + 1 = 1
    - A • 0 = 0
3. **Idempotent Law**
    - A + A = A
    - A • A = A
4. **Complement Law**
    - A + A′ = 1
    - A • A′ = 0
5. **Double Complement Law**
    - (A′)′ = A
6. **Commutative Law**
    - A + B = B + A
    - A • B = B • A
7. **Associative Law**
    - (A + B) + C = A + (B + C)
    - (A • B) • C = A • (B • C)
8. **Distributive Law**
    - A • (B + C) = (A • B) + (A • C)
    - A + (B • C) = (A + B) • (A + C)

---

## 5. Important Boolean Theorems

### a) De Morgan’s Theorems

1. (A + B)′ = A′ • B′
    - Complement of OR → AND of complements.
2. (A • B)′ = A′ + B′
    - Complement of AND → OR of complements.

**Examples:**

- If A=1, B=0 →
    - (A + B)′ = (1+0)′ = 1′ = 0
    - A′ • B′ = (0 • 1) = 0 ✅

---

## 6. Simplification of Boolean Expressions

- Purpose: Reduce circuit complexity.
- Apply Boolean laws & theorems.
- Benefits:
    - Fewer logic gates.
    - Faster circuits.
    - Lower cost and power consumption.

Example:  
(A + A′ • B) = (A + B)  
(using Absorption + Complement laws)
```embed
title: "Boolean Algebra Examples (Part 1)"
image: "https://i.ytimg.com/vi/k04ksfLBuak/maxresdefault.jpg"
description: "Digital Electronics: Solved questions on Boolean algebra.Topics discussed:1) Minimization of AB + AB'2) minimization of AB + AB'C + AB'C'Follow Neso Academy ..."
url: "https://youtu.be/k04ksfLBuak"
favicon: ""
aspectRatio: "56.25"
```

---

## 7. Boolean Algebra in Digital Logic Design

- Logic gates implement Boolean operations:
    - AND gate → multiplication (•).
    - OR gate → addition (+).
    - NOT gate → inversion (′).
- Complex circuits built by combining gates.
- Boolean algebra → allows **design, analysis, and optimization**.

---

## 8. Summary

- Boolean variables → two values (0,1).
- Basic operations:
    - AND (•) → true if both are true.
    - OR (+) → true if any one is true.
    - NOT (′) → inverts.
- Laws (Identity, Null, Complement, etc.) → simplify expressions.
- Theorems (De Morgan’s) → rewrite negated expressions.
- Simplification → fewer gates, efficient circuits.
- Boolean algebra = backbone of **digital logic design**.
![[Pasted image 20250826095331.png]]
---