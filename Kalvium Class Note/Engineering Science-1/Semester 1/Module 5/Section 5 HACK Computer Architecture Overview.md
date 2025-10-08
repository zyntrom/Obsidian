## 🧠 Lesson 5.5 — HACK Computer Architecture Overview

### 🌟 Learning Objectives

By the end of this lesson, you should be able to:

1. Describe the **Hack computer architecture** and its core components: CPU, memory, input/output.
2. Distinguish **Harvard** vs. **Von Neumann architectures**.
3. Identify the two main Hack instruction types: **A-instructions** and **C-instructions**.
4. Decode the **binary format** of Hack machine instructions.
5. Explain the **program counter’s** role.
6. Illustrate the **fetch-decode-execute cycle**.
7. Trace a sample program step-by-step on the Hack computer.

---

## 🖥️ The Hack Computer Model

- A **16-bit educational computer** designed for learning.
- Central to the **nand2tetris course**, enabling building a computer from **NAND gates** up to a software stack.
- Includes:
    - **CPU** → executes instructions using **ALU** and **registers**
    - **Memory** → stores instructions and data
    - **Input/Output** → interacts with the outside world
- Purpose: teach core computing concepts without extra complexity.

---

## 🏗️ Harvard vs Von Neumann Architectures

- **Von Neumann:** single memory for data + instructions → flexible but slower due to potential bottlenecks.
- **Harvard:** separate memory for data and instructions → faster, but more hardware complexity.
- Hack blends aspects of both → ideal for teaching.

---

## 🔹 Core Hack CPU Components

1. **ALU (Arithmetic Logic Unit):** performs arithmetic (ADD, SUB) and logic (AND, OR) operations.
2. **Registers:**
    - **A:** stores memory addresses or data
    - **D:** stores data for computation
3. **Memory:** separated into instruction memory and data memory.

- These components collaborate to fetch, decode, and execute instructions.

---

## 📝 Hack Instruction Types

1. **A-instructions:** set **A register** to a value.
    - Syntax: `@value` (e.g., `@10` loads 10 into A)
2. **C-instructions:** perform computations and conditional jumps.
    - Syntax: `dest=comp;jump`
        - `dest` → where to store result (A, D, or M)
        - `comp` → computation (e.g., D+A)
        - `jump` → flow control (e.g., JGT: jump if greater than zero)

---

## 💻 Instruction Format

- **A-instruction:** starts with `0`, followed by 15-bit value
    - Example: `@10` → `0000000000001010`
- **C-instruction:** starts with `111`, followed by bits for computation, destination, and jump
    - Example: `D=D+A` → `1111000010010000`

---

## 🔄 Program Counter (PC)

- Holds the **address of the next instruction**.
- PC increments after each instruction → sequential execution.
- Conditional/unconditional jumps modify PC → control loops and logic flow.

---

## 🔁 Fetch-Decode-Execute Cycle

1. **Fetch:** CPU reads instruction from memory using PC.
2. **Decode:** CPU interprets instruction → determines operation and operands.
3. **Execute:** ALU, registers, and memory perform the operation.
4. Repeat for next instruction.

---

## ⚡ Running a Sample Program

Program to sum two numbers and store the result:

```c
@2       // A = 2
D=A      // D = 2
@3       // A = 3
D=D+A    // D = 5
@16      // A = 16 (memory address)
M=D      // Store D into memory[16]

```

**Step-by-step:**

1. Load constants into registers.
    
2. Perform addition in ALU.
    
3. Store result in RAM.
    
4. Demonstrates interaction of **registers, ALU, and memory**.
    

---

## ✅ Summary

- Hack simplifies computer architecture: **CPU, memory, I/O**.
    
- Blends **Harvard** and **Von Neumann** concepts.
    
- Instructions: **A-instruction** → load values, **C-instruction** → computations & jumps.
    
- Instructions = **16-bit binary words**, executed cycle-by-cycle.
    
- **Program counter** manages instruction order.
    
- Fetch-decode-execute cycle drives all computation.
    

---

## 🎁 Bonus Content

- Hack Computer Model | Wikipedia
    
- Harvard vs Von Neumann Architectures Explained | Spiceworks
    
- Hack Computer Language and Tools | Official Project Site