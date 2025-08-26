# Logic Gates and Truth Tables

## 1. Recap: Boolean Algebra Basics

- Boolean values: **0 (False), 1 (True)**.
- Important Laws:
    - **Identity Law**: A • 1 = A ; A + 0 = A
    - **Null Law**: A • 0 = 0 ; A + 1 = 1
    - **Domination Law**: Emphasizes effect of 0 (in AND) and 1 (in OR).
    - **Idempotent Law**: A • A = A ; A + A = A
    - **Complement Law**: A • A′ = 0 ; A + A′ = 1
    - **Double Negation Law**: (A′)′ = A
    - **Commutative Law**: A + B = B + A ; A • B = B • A
    - **Associative Law**: (A + B) + C = A + (B + C) ; (A • B) • C = A • (B • C)
    - **Distributive Law**: A • (B + C) = (A • B) + (A • C) ; A + (B • C) = (A + B) • (A + C)
- **De Morgan’s Theorems**:
    - (A • B)′ = A′ + B′
    - (A + B)′ = A′ • B′

---

## 2. Logic Gates – The Building Blocks

- **Definition**: Physical devices that implement Boolean operations.
- **Inputs**: One or more binary values (0/1).
- **Output**: Single binary value.
- **Analogy**: Gates are like electronic switches controlling current flow.

### a) Basic Gates

1. **AND Gate (•)** → Output = 1 if _all_ inputs = 1.
2. **OR Gate (+)** → Output = 1 if _any_ input = 1.
3. **NOT Gate (′)** → Inverts input (0 → 1, 1 → 0).

### b) Universal Gates

- Called _universal_ because **any circuit** can be built using only them.

1. **NAND Gate** = NOT(AND).
    - Output = 0 only if all inputs = 1.
```embed
title: "NAND gate as Universal Gate"
image: "https://i.ytimg.com/vi/cNFgilYDxuA/maxresdefault.jpg"
description: "In this video, different logic gates (AND, OR, NOT, XOR, etc.) are implemented using only NAND gates. The following topics are covered in the video:0:00 Intr..."
url: "https://youtu.be/cNFgilYDxuA"
favicon: ""
aspectRatio: "56.25"
```
![[Pasted image 20250826100103.png]]
1. **NOR Gate** = NOT(OR).
    - Output = 1 only if all inputs = 0.
```embed
title: "NOR Gate as Universal Gate"
image: "https://i.ytimg.com/vi/nLzmWuGRCok/maxresdefault.jpg"
description: "In this video, the different logic gates (AND, OR, NOT, XOR, XNOR, etc.) are implemented using the NOR gate alone. The following topics are covered in the vi..."
url: "https://youtu.be/nLzmWuGRCok"
favicon: ""
aspectRatio: "56.25"
```

![[Pasted image 20250826100111.png]]

### c) Derived Gates

1. **XOR (Exclusive OR)**
    - Output = 1 if inputs are **different**.
    - Example: 0 ⊕ 1 = 1 ; 1 ⊕ 1 = 0.
![[Pasted image 20250826100137.png]]
2. **XNOR (Exclusive NOR)**
    - Output = 1 if inputs are **same**.
    - Opposite of XOR.
![[Pasted image 20250826100144.png]]

---

## 3. Truth Tables

- Show **all possible input combinations** and corresponding outputs.
- Example: XOR gate

| A   | B   | A ⊕ B |
| --- | --- | ----- |
| 0   | 0   | 0     |
| 0   | 1   | 1     |
| 1   | 0   | 1     |
| 1   | 1   | 0     |

**Usefulness:**

- Acts as a “recipe” → ensures predictable logic.
- Helps check if two Boolean expressions are equivalent.
![[Pasted image 20250826100153.png]]
---

## 4. Combining Logic Gates

- Complex Boolean expressions can be **converted into gate circuits**.
- Example: F = ¬(A • B)
    - Step 1: A • B → AND gate.
    - Step 2: ¬(result) → NOT gate.
    - Equivalent to a **NAND gate**.

---

## 5. Circuit Implementation

- Boolean expression = **blueprint**.
- Logic gates = **bricks**.
- Example: (A • B) + C′ → circuit with:
    - AND gate (A,B).
    - NOT gate (C′).
    - OR gate for final output.

---

## 6. Simplification Techniques

- **Boolean rules** reduce gate count.
- Example: A + A′B = A + B (Absorption Law).
- **Karnaugh Maps (K-Maps):**
    - Visual method to minimize Boolean expressions.
    - Efficient for circuits with multiple variables.
```embed
title: "Karnaugh Maps – Simplify Boolean Expressions"
image: "https://i.ytimg.com/vi/UfZKvPQku8w/maxresdefault.jpg?sqp=-oaymwEmCIAKENAF8quKqQMa8AEB-AH-CYAC0AWKAgwIABABGGUgZShlMA8=&rs=AOn4CLDiYCTi3lqpDJAt1Hl_Z_WcSK5SuA"
description: "This video follows on from the previous videos about Karnaugh maps.  It explains how Karnaugh maps, and truth tables, can be used to simplify complex Boolean..."
url: "https://youtu.be/UfZKvPQku8w"
favicon: ""
aspectRatio: "56.25"
```

---

## 7. Practical Applications

- **Computers & processors** → arithmetic & logic operations.
- **Calculators** → implement add/subtract using gates.
- **Voting machines** → count & compare inputs.
- **Smart devices** → sensors + logic gates for decision-making.

---

## 8. Summary

1. Logic gates implement Boolean algebra in hardware.
2. Basic gates: AND, OR, NOT.
3. Universal gates: NAND, NOR (can build any circuit).
4. Derived gates: XOR, XNOR (special cases for equality/difference).
5. Truth tables → show input-output relationships.
6. Circuits are designed by converting Boolean expressions into gates.
7. Simplification (Boolean rules + K-Maps) → reduces complexity.
8. Applications → digital devices, computers, automation.
![[Pasted image 20250826100214.png]]