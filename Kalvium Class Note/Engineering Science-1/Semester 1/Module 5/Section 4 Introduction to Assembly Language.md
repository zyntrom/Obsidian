## 🧠 Lesson 5.4 — Introduction to Assembly Language

### 🌟 Learning Objectives

By the end of this lesson, you should be able to:

1. Define **assembly language** and its relevance.
2. Differentiate **assembly** from machine code and understand how **assemblers** work.
3. Identify the **structure and components** of an assembly program.
4. Describe the roles of **registers** and **memory**.
5. List types of assembly instructions and their uses.
6. Walk through a simple assembly program.
7. Understand advantages and limitations of assembly programming.

---

## 🖥️ What is Assembly Language?

- Low-level language **one step above machine code**.
- Uses **mnemonics** instead of raw binary to make instructions human-readable.
- Each line typically maps to **one machine instruction**.
- Provides **direct control** over hardware → used in embedded systems, device drivers, performance-critical software.

**Example:**

```c
MOV AX, 1   ; Move value 1 into AX register
ADD AX, 2   ; Add 2 to AX register
```

- `MOV` and `ADD` → mnemonics (actions)
- `AX` → CPU register (fast storage inside CPU)
```embed
title: "Introduction to Assembly Language Tutorial"
image: "https://i.ytimg.com/vi/0nZauIwn-xo/maxresdefault.jpg"
description: "Introduction to assembly language tutorial is a tutorial that covers the introduction to what is assembly language, must know basic information, and  what yo..."
url: "https://youtu.be/0nZauIwn-xo"
favicon: ""
aspectRatio: "56.25"
```

---

## 🔹 Assembly Structure & Components

Each assembly statement can have:

1. **Label (optional):** symbolic memory address → for loops/jumps.
2. **Instruction (required):** mnemonic operation (MOV, ADD, JMP).
3. **Operands (optional):** data/registers/memory to act on.
4. **Comment (optional):** starts with `;` for readability.

**Format:**

```c
label: instruction operand1, operand2 ; comment
```

**Example:**

```c
start:          ; Label marking program start
    MOV AX, 10  ; Load 10 into AX
    ADD AX, BX  ; Add BX to AX
    JMP start   ; Jump to 'start'

```

---

## 🛠️ Registers vs Memory

- **Registers:** Tiny, ultra-fast CPU storage. Used for immediate operations.
    - Common: AX, BX, CX, DX (general-purpose), SP (stack pointer), BP (base pointer), IP (instruction pointer)
- **Memory:** Larger, slower storage. Labels used to access memory.

**Example:**

```js
section .data
    myVar DW 1234  ; Define a variable in memory

section .text
_start:
    MOV AX, [myVar] ; Load value from memory into AX

```

---

## ⚡ Instruction Types

1. **Data Movement:** MOV, LEA, PUSH, POP
2. **Arithmetic:** ADD, SUB, MUL, DIV
3. **Logical / Bitwise:** AND, OR, XOR, NOT
4. **Control Flow:** JMP, JE, JNE, CALL, RET

**Example:**

```c
MOV AX, 5       ; data movement
ADD AX, 3       ; arithmetic
AND AX, 0x0F    ; bitwise operation
CMP AX, 10      ; compare
JE equal        ; conditional jump

```

---

## 🖇️ Program Walkthrough

Program to add two numbers:

```c
section .data
    num1 DW 10
    num2 DW 20
    result DW 0

section .text
    global _start

_start:
    MOV AX, [num1] ; Load num1 into AX
    MOV BX, [num2] ; Load num2 into BX
    ADD AX, BX     ; AX = AX + BX
    MOV [result], AX ; Store result
    MOV EAX, 1     ; System call for exit
    XOR EBX, EBX   ; Return 0 status
    INT 0x80       ; Interrupt to kernel

```

**Steps:**

1. Define data variables.
2. Load values into registers.
3. Perform computation (ADD).
4. Store result in memory.
5. Exit program.

---

## ✅ Advantages

- High performance & low overhead.
- Precise control over CPU and hardware.
- Critical for **system software**, embedded applications, and optimization.

## ⚠️ Limitations

- Complex & time-consuming to write.
- Hardware-specific → low portability.
- Hard to maintain & read in large programs.

---

## 🔑 Summary

- Assembly = **human-readable machine code**.
- Assembler translates mnemonics → machine instructions.
- Programs = labels, instructions, operands, comments.
- Registers = fast CPU storage; memory = slower but larger.
- Instructions: **data movement, arithmetic, logical, control flow**.
- Powerful but complex → used for performance-critical tasks.

---

## 🎁 Bonus Content

- [Assembly Language | YouTube](https://www.youtube.com)
- Registers and Memory | Ahirlabs
- Components | Indeed

![[Pasted image 20251008164600.png]]