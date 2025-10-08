## 🧠 Lesson 5.6 — Writing Assembly for HACK Architecture

### 🌟 Learning Objectives

By the end of this lesson, you should be able to:

1. Understand the **syntax and structure** of HACK assembly (**A- and C-instructions**).
2. Load constants, addresses, and symbols into the **A-register** using A-instructions.
3. Use C-instructions for arithmetic, logic, memory, and program flow operations.
4. Read from/write to memory and manipulate data in registers.
5. Use **jumps, labels, and loops** to control program flow.
6. Build, debug, and optimize simple Hack programs.

---

## 🖋️ Understanding HACK Assembly Syntax

- HACK assembly has **two instruction types**:
    1. **A-instructions:** `@value` → load constants, addresses, or symbolic labels into **A-register**.
    2. **C-instructions:** `dest=comp;jump` → perform computation, store results, and optionally jump.
- **Analogy:**
    - A-instructions → “setting the destination” (what/where to work on)
    - C-instructions → “deciding what to do” and “where to go next”

---

## 🔹 Mastering A-Instructions

- Syntax: `@value`
    - Example: `@10` → A-register = 10
    - Example with symbol: `@counter` → A-register = address of `counter`
- **Use cases:**
    - Set memory addresses for read/write
    - Specify constants for computation
    - Act as indirect address (`M` refers to memory at address in A)
- **Pro tip:** use **symbolic labels** for readability and maintainability.

**Example:**

```c
@15      // Load 15 into A
D=A      // D register = 15
@counter // Load address of 'counter' into A
M=D      // Store D at memory[counter]

```

---

## 🔹 Dissecting C-Instructions

- General format: `dest = comp ; jump`
    - **dest:** where to store result (A, D, M, or combination)
    - **comp:** computation (D+1, A-1, D|A, etc.)
    - **jump:** condition for program counter (JGT, JEQ, JLT, JMP)
- **How it works:**
    - If jump condition is true → set PC to address in A-register
        
    - Otherwise → continue to next instruction
        
- **Examples:**
    

`D=A+1      // Compute A+1 → D M=D        // Store D at memory[A] D;JLT      // If D < 0 → jump 0;JMP      // Unconditional jump`

---

## 🔹 Using Labels & Loops

- Labels: `(LOOP)` → marks a memory location
    
- Jumps: `@LOOP` + `0;JMP` → repeat execution
    
- Example loop to increment a counter:
    

`@0 M=M+1     // Increment counter @LOOP 0;JMP     // Repeat loop  (END) @END 0;JMP     // Halt`

---

## 🔹 Optimization & Exploration

- Modify loops to count higher (e.g., up to 20)
    
- Use nested loops for advanced patterns (e.g., times-table)
    
- Reuse memory locations to save space
    
- Minimize jumps for efficiency
    

---

## ✅ Summary

- **A-instructions** → set addresses/constants
    
- **C-instructions** → arithmetic, logic, memory, and jumps
    
- **Labels & symbolic variables** → readable and flexible code
    
- **Jumps** → enable loops and conditional execution
    
- Combining memory and program flow → build efficient Hack programs
    
- Practice builds **muscle memory** for low-level programming
    

---

## 🎁 Bonus Content

- Hack's Assembly Language | jk quantified
    
- [How Hack Assembly Works | YouTube](https://www.youtube.com)
    
- [Writing an Assembler | YouTube](https://www.youtube.com)