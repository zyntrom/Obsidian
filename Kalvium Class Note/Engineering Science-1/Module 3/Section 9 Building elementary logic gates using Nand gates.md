# Building Elementary Logic Gates Using NAND Gates – Notes

## Learning Objectives

- Understand **NAND gate as a universal gate**
- Construct **NOT, AND, OR, NOR, XOR, XNOR** gates using NAND gates
- Analyze logic and circuit design for gate conversions
- Interpret **truth tables & logic expressions**
- Apply NAND logic for simplified digital circuit design

---

## Why Learn NAND Gate Conversions?

- **Universal Gate** → Like a LEGO brick, can build all other gates
- **Optimization** → Use only one gate type → reduces manufacturing cost
- **Fault Tolerance** → Easy replacement (only one gate type needed)
- **Efficient Computation** → NAND-based circuits are fast & reliable
- **Fundamental Knowledge** → Crucial for debugging & custom circuit design

---

## NAND Gate Basics

- **Definition:** Opposite of AND gate
- **Formula:** A NAND B = (A · B)’
- **Output Rule:** Gives 0 only when both inputs are 1
![[Pasted image 20250826102625.png]]

### Truth Table – NAND

| A   | B   | A·B | (A·B)’ |
| --- | --- | --- | ------ |
| 0   | 0   | 0   | 1      |
| 0   | 1   | 0   | 1      |
| 1   | 0   | 0   | 1      |
| 1   | 1   | 1   | 0      |

---

## Constructing Gates from NAND

### 1. NAND → NOT Gate
- Connect both inputs together: A = B
- Output: (A·A)’ = A’
- **Rule:** NAND with tied inputs works as NOT
![[Pasted image 20250826102635.png]]
---

### 2. NAND → AND Gate
- Step 1: NAND gives (A·B)’
- Step 2: Pass through NOT → ((A·B)’)’ = A·B
- **Rule:** AND = NAND + NOT
![[Pasted image 20250826102642.png]]
---

### 3. NAND → OR Gate
- Step 1: Invert inputs → A’ , B’
- Step 2: NAND the results → (A’·B’)’ = A + B
- **Rule:** OR = NAND(NOT(A), NOT(B))
![[Pasted image 20250826102651.png]]

```embed
title: "NAND gate as Universal Gate"
image: "https://i.ytimg.com/vi/cNFgilYDxuA/maxresdefault.jpg"
description: "In this video, different logic gates (AND, OR, NOT, XOR, etc.) are implemented using only NAND gates. The following topics are covered in the video:0:00 Intr..."
url: "https://youtu.be/cNFgilYDxuA"
favicon: ""
aspectRatio: "56.25"
```

---

### 4. NAND → NOR Gate
- Step 1: Create OR (from NAND)
- Step 2: Add NOT → (A + B)’
- **Rule:** NOR = NOT(OR)

---

## Exclusive Gates (Complex)

### 5. NAND → XOR Gate
Steps:
1. NAND1 = (A·B)’
2. NAND2 = (A·NAND1)’
3. NAND3 = (B·NAND1)’
4. NAND4 = (NAND2·NAND3)’ → Final XOR

### XOR Truth Table

| A   | B   | NAND1 | NAND2 | NAND3 | XOR |
| --- | --- | ----- | ----- | ----- | --- |
| 0   | 0   | 1     | 1     | 1     | 0   |
| 0   | 1   | 1     | 1     | 0     | 1   |
| 1   | 0   | 1     | 0     | 1     | 1   |
| 1   | 1   | 0     | 1     | 1     | 0   |

---

### 6. NAND → XNOR Gate

- XNOR = NOT(XOR)
- Build XOR from NAND, then add NOT
- **Rule:** XNOR = XOR + NOT

---

## Summary

- **NAND = Universal Gate**
- **Conversions:**
    - NOT → Tie inputs
    - AND → NAND + NOT
    - OR → NAND(NOT(A), NOT(B))
    - NOR → OR + NOT
    - XOR → 4 NAND combination
    - XNOR → XOR + NOT
- **Applications:** CPUs, memory units, efficient circuit design