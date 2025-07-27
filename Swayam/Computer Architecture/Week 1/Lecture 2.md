# 🧠 Introduction to Computer Architecture – Lecture 1 (Part 2)

**Course**: Computer Organization and Architecture  
**Based on**: McGraw-Hill, 2015 Edition  
**Focus**: Core structure of a computer system, memory, and instruction cycle.

---

## 🔷 What is a Computer System?

- A **computer system** includes **hardware**, **software**, and **firmware** that work together to perform computation.
- These components are organized into a **well-defined structure** that allows the system to execute user instructions efficiently.

---

## 💾 Memory and Instruction Execution

### 🔹 Program Storage and Execution

- A computer program is a sequence of instructions stored in **main memory (RAM)**.
- **Processor (CPU)** fetches these instructions **one by one**, decodes them, and **executes** them.
- Example: Instructions like `Add`, `Move`, or `Jump` are executed from memory.

### 🔹 Instruction Cycle (Fetch–Decode–Execute)

1. **Fetch**: CPU fetches the instruction from main memory.
2. **Decode**: Control unit decodes the fetched instruction.
3. **Execute**: ALU or other functional units execute the decoded operation.
4. **Repeat**: Moves to the next instruction using the **Program Counter (PC)**.

### 🔸 Role of the Program Counter (PC)

- PC keeps track of the **next instruction** to be fetched from memory.
- After executing an instruction, PC increments to point to the next one.
- For a **jump instruction**, PC may be updated with a different address.

---

## 🏗️ Basic Structure of a Computer System

A computer system consists of **four major components**:

### 1. **Central Processing Unit (CPU)**

- Often called the **processor** or **brain** of the computer.
- Contains:
    - **Arithmetic Logic Unit (ALU)**: Performs arithmetic and logic operations.
    - **Control Unit (CU)**: Directs operations by interpreting instructions.
    - **Registers**: Small, fast memory units inside the CPU (e.g., accumulator, instruction register).

### 2. **Memory Unit**

- Holds **instructions** and **data**.
- Includes:
    - **Primary memory** (RAM)
    - **Secondary memory** (hard drives, SSDs)
- Memory is organized in a linear fashion with unique **addresses**.

### 3. **Input/Output (I/O) Devices**

- Allow communication between the computer and the external world.
    - **Input**: Keyboard, mouse, sensors
    - **Output**: Monitor, printer, actuators

### 4. **Interconnection (Bus System)**

- Connects CPU, memory, and I/O.
- Three main types of buses:
    - **Data bus**: Carries data.
    - **Address bus**: Carries address of memory locations.
    - **Control bus**: Carries control signals like Read/Write.

---

## 🔄 Example of Instruction Execution

### Instruction: `ADD A, B`

- Meaning: Add contents of register A and register B, store result in A.
- Steps:
    1. CPU fetches the `ADD` instruction from memory.
    2. It decodes to understand: operation = addition, operands = A and B.
    3. ALU adds values.
    4. Result is stored back in register A.

---

## 📝 Summary

- Instructions are stored in memory and executed one at a time using the **fetch-decode-execute cycle**.
- CPU is responsible for **processing**, memory stores instructions and data, I/O connects with external world, and **buses interconnect** components.
- **Program Counter (PC)** manages instruction flow.
- Understanding this cycle and component structure is essential for learning deeper architecture topics like pipelining, cache, and control units.