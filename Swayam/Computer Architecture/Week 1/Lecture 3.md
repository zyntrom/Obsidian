# 🧠 Computer Architecture – Lecture 1 (Part 3)

**Course**: Computer Organization and Architecture  
**Based on**: McGraw-Hill, 2015 Edition  
**Focus**: Block diagram of a computer system, buses, and instruction flow.

---

## 🧱 Block Diagram of a Computer System

A simplified **block diagram** of a computer consists of:

### 1. **Central Processing Unit (CPU)**

- **Controls and executes** all system operations.
- Contains:
    - **ALU** (Arithmetic Logic Unit): Performs computation.
    - **Control Unit**: Directs activities.
    - **Registers**: Temporarily store data and addresses.

### 2. **Memory Unit**

- **Main memory** (RAM): Temporarily stores:
    - Instructions
    - Data
    - Intermediate results
- Each memory location has a **unique address**.

### 3. **Input Devices**

- Send data to memory or CPU (e.g., keyboard, mouse).

### 4. **Output Devices**

- Receive data from memory or CPU (e.g., monitor, printer).

---

## 🔁 Flow of Data and Instructions

### Step-by-step flow:

1. **Input Device** → sends data to → **Main Memory**
2. **CPU** fetches data from memory
3. **ALU** performs operations
4. Result stored back in memory or sent to **Output Device**

---

## 🧠 Example: Adding Two Numbers

Let’s say the task is to **add two numbers from memory**:

### Memory layout:

|Address|Content|
|---|---|
|100|5|
|101|10|
|102|`ADD 100, 101` (instruction)|

### Execution flow:

1. CPU fetches instruction from memory address `102`.
2. Instruction says: add value at `100` and `101`.
3. ALU adds values: 5 + 10 = 15
4. Result is stored at a new location (e.g., address `103`) or output.

---

## 🔌 Interconnections – Buses

A **bus** is a set of parallel lines (wires) that connect components in the system.

### Types of Buses:

|Bus Type|Purpose|
|---|---|
|**Data Bus**|Transfers data between CPU, memory, I/O|
|**Address Bus**|Carries memory addresses|
|**Control Bus**|Carries control signals (Read/Write, etc.)|

- All major units—**CPU**, **Memory**, and **I/O**—communicate via these buses.

---

## 🔧 Role of Control Unit

- The **Control Unit** acts like a manager.
- It:
    - Coordinates instruction fetch, decode, execute
    - Sends signals over the control bus to memory and I/O
    - Decides when to read or write

---

## 📌 Key Terms Summary

|Term|Meaning|
|---|---|
|**Instruction**|A command to perform a specific operation (e.g., `ADD`)|
|**Program Counter (PC)**|Points to the address of the next instruction|
|**Fetch**|Getting the instruction from memory|
|**Decode**|Interpreting what the instruction means|
|**Execute**|Performing the operation|

---

## 📝 Summary

- Computer operations rely on **memory**, **CPU**, and **buses**.
- **Instructions** reside in memory and are executed step-by-step.
- The **control unit** and **buses** coordinate the movement of data and instructions.
- Every component plays a specific role in enabling computation.