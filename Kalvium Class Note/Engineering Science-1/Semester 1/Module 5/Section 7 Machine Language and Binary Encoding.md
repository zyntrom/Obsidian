## 🧠 Lesson 5.7 — Machine Language and Binary Encoding

### 🌟 Learning Objectives

By the end of this lesson, you should be able to:

1. Describe what **machine language** is and why computers need **binary encoding**.
2. Understand the **HACK instruction set** and how A- and C-instructions are represented in binary.
3. Translate HACK assembly code into **16-bit binary machine code**.
4. Use encoding tables to map mnemonics (instructions) to binary fields.
5. Avoid common mistakes in manual binary encoding.
6. Verify machine code using simulators or hands-on testing.

---

## 🔹 Understanding Machine Language

- Machine language is the **only language CPUs understand**: sequences of 0s and 1s.
- Every operation (arithmetic, memory access, jump) is ultimately a **binary instruction**.
- Assembly language is a “stepping stone”: easier to write/read, then translated to machine language.
- Analogy: **Machine language** is like Morse code for computers—exact sequences, no ambiguity.
```embed
title: "[Part 1] Unit 4.1 - Machine Languages: Overview"
image: "https://i.ytimg.com/vi/UzezuWXRRCw/hqdefault.jpg"
description: "Created by:  Hebrew University of JerusalemTaught by: Simon Schocken and Noam NisanLinks:https://www.coursera.org/learn/build-a-computerhttp://www.nand2tetri..."
url: "https://youtu.be/UzezuWXRRCw"
favicon: ""
aspectRatio: "75"
```

---

## 🔹 The Assembler

- Converts assembly code into binary **machine instructions**.
- Steps of assembly:
    1. **Lexical analysis** – split code into tokens.
    2. **Syntax analysis** – check instruction grammar.
    3. **Semantic analysis** – resolve labels & variables to addresses.
    4. **Code generation** – produce 16-bit machine code.
- Output: `.hack` or similar file with binary instructions ready to execute.
- Each assembly line = **one 16-bit instruction**.

---

## 🔹 HACK Instruction Types

### 1️⃣ A-instructions

- Syntax: `@value` (number or label).
- **Machine code format:**
    - Leading 0 + 15-bit binary value.
    - Example: `@10` → `0000000000001010`
- Steps to encode:
    1. Convert decimal to 15-bit binary.
    2. Add leading 0 → 16-bit instruction.

### 2️⃣ C-instructions

- Syntax: `dest = comp ; jump`
- **Machine code format:**
    - Leading `111` + 13-bit fields: `a c1-c6 d1-d3 j1-j3`
        - **a-bit:** 0 = use A, 1 = use M
        - **c1-c6:** computation
        - **d1-d3:** destination registers (A, D, M)
        - **j1-j3:** jump condition (JGT, JEQ, JMP…)
- Example: `D=A+1` → `1110110110010000`

---

## 🔹 Binary Encoding Details

|Field|Bits|Purpose|
|---|---|---|
|**comp**|6|Operation (e.g., D+A, D|
|**dest**|3|Destination registers: A, D, M|
|**jump**|3|Conditional jumps: JGT, JEQ, JMP|

- **Destination bits example:**
    - 000 → null
    - 010 → D
    - 100 → A
    - 111 → A, D, M
- **Jump bits example:**
    
    - 000 → no jump
    - 001 → JGT
    - 010 → JEQ
    - 111 → JMP

---

## 🔹 Hands-On Translation

Example translations:

|Assembly|Explanation|Binary|
|---|---|---|
|`D=A+1`|Add 1 to A, store in D|`1110110110010000`|
|`M=D`|Store D into memory[A]|`1110001100001000`|
|`@10`|Load 10 into A|`0000000000001010`|
|`0;JMP`|Unconditional jump|`1110101010000111`|

**Key Steps:**

1. Identify instruction type.
2. Map comp, dest, jump to binary.
3. Assemble 16-bit instruction.

---

## 🔹 Example: Executing Binary Instructions

Given binary instructions:

```c
00010010 // LOAD 2 into A
00100011 // ADD 3 to A
00110000 // STORE A in memory[0]

```

Step-by-step:

1. LOAD → Register A = 2
2. ADD → Register A = 2+3 = 5
3. STORE → Memory[0] = 5

Analogy: Pressing a microwave button → CPU executes machine code step by step.

---

## 🔹 Common Mistakes to Avoid

- Wrong 15-bit conversion for A-instructions
- Confusing **A vs M** in comp field
- Wrong destination or jump bits
- Forgetting the C-instruction opcode `111`
- Misordering fields or typos

✅ Always check using the **HACK assembler** or simulator.

---

## 🔹 Verification & Validation

- Use a **simulator** to check correctness.
- Debug: step through instructions, check memory and register states.
- Compare hand-encoded binary with assembler output.

---

## ✅ Summary

- Machine language = CPU’s native code (0s & 1s)
- A-instructions: `0 + 15-bit value`
- C-instructions: `111 + comp + dest + jump`
- Translating assembly → binary is systematic but requires care
- Validation using simulators ensures correctness

---

## 🎁 Bonus Content

- HACK Assembly to Machine Code | Official Nand2Tetris Guide
- Binary Encoding | Ontosight
- Assembly Language & Machine Code Process Explained | Cratecode

![[Pasted image 20251008170053.png]]