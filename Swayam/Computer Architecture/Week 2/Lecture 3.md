# 🧠 Chapter 3: Assembly Language – Simple RISC ISA

**From the course: Computer Organization and Architecture (SWAYAM)**

---

## 🔹 What is Assembly Language?

- **Assembly language** is the **interface between software and hardware**.
- It allows precise **control over the hardware** and helps understand how computers execute programs at a low level.
- Real-world ISAs (Instruction Set Architectures) are complex (e.g., x86, ARM), so a **simplified ISA** is used for educational purposes in this course.

---

## 🔹 Why Study a Simple ISA First?

- Real ISAs involve **hundreds of instructions** and complex encoding rules.
- This course designs and uses a **Simple RISC ISA**:
    - Easier to understand and implement
    - Enough to learn fundamentals like:
        - Instruction encoding
        - Binary format
        - Register usage
        - Arithmetic, logical, control instructions

---

## 🔹 Instruction Set Architecture (ISA)

- **ISA** defines:
    - What instructions a processor can execute
    - How instructions are represented in binary
    - How memory, registers, and control flow are handled
- Assembly Language is the **textual version** of machine instructions defined by an ISA.

---

## 🔹 Historical Instruction Sets

|ISA|Year|Bit Width|Registers|Endianness|Features|
|---|---|---|---|---|---|
|**VAX**|1977|-|16|Little Endian|CISC architecture, complex encoding|
|**SPARC**|1986|32-bit|32|Bi-endian|Simple RISC design|
||1993|64-bit||||
|**PowerPC**|1992|32 → 64|32|Bi-endian|Used in IBM systems, Apple (earlier)|

---

## 🔹 Design of Simple RISC Assembly Language

### 🧱 Features:

- **RISC (Reduced Instruction Set Computer)**: Few, simple, fixed-size instructions
- Fixed **32-bit instruction format**
- **Registers only** – no memory-to-memory operations
- Mostly **3-register instructions**

### 🧾 Instruction Categories:

1. **Arithmetic Instructions**
    - `add`, `sub`, `mul`, `div`
2. **Logical Instructions**
    - `and`, `or`, `not`, `xor`
3. **Data Movement**
    - `load`, `store`, `mov`
4. **Branching & Control Flow**
    - `jmp`, `beq`, `bne`, `blt`, `bgt`

---

## 🔹 Sample Instruction Format (Hypothetical)

For a 3-register instruction like `add r1, r2, r3`:

- **Binary Layout**:
    - `[Opcode (6 bits)][r1 (5 bits)][r2 (5 bits)][r3 (5 bits)][Unused/Padding]`
- Total: 32 bits per instruction

---

## 🔹 Purpose of Simple RISC Assembly

- Designed for **educational clarity**, not real-world performance
- You will:
    1. **Write assembly programs** using this ISA
    2. **Translate** them into binary
    3. Later, **build a processor** that executes them

---

## 🔹 Summary of Key Points

- Assembly language is crucial for understanding how **hardware executes software**.
- Real-world ISAs are complex; hence, a **simple RISC ISA** is designed for this course.
- You will learn:
    - Designing instruction formats
    - Converting assembly to binary
    - Implementing ISA in hardware in future chapters