# 🧠 Course Introduction: C Programming and Assembly Language

---

## 🎯 Motivation for the Course

- Many students learn **C programming** and **assembly language** **separately**, but there’s a **missing bridge** between the two.
- Students often **don’t understand**:
    - How a C program **executes** on a microprocessor.
    - What physically happens in **memory segments** (stack, heap, etc.).
- Common misconceptions:
    - Students say local variables are on the stack—but don't **understand what that means** physically.
    - They use terms like **local scope/global scope** without connecting them to memory operations.

---

## 🎓 Course Objectives

The course aims to **physically demonstrate** how C code gets executed on a microprocessor using:

- **Simple examples**
- **Animations**
- **Inline assembly programming**

---

## ✅ Learning Outcomes

After completing the course, you will be able to:

1. 🔍 Explain how **function calls** are translated to assembly.
2. 📦 Explain how **parameters are passed** to functions.
3. 🧠 Understand what it means to say **local variables are stored on the stack**.
4. 🛠️ Demonstrate how **local variable space is allocated** by the compiler.
5. 🧼 Explain how local variables **go out of scope** after a function exits.
6. 🧾 List assembly instructions that execute **before entering** and **after exiting** a function (prologue/epilogue).
7. 🔄 Understand **C calling conventions**, especially:
    - Fixed argument list
    - Variable argument list
8. 🆚 Compare **C and C++** at the assembly level.
9. 🚀 Use **hardware-level instructions** to **optimize C functions**.
10. ⚠️ Explain **why recursion** may be inefficient in assembly-level execution.

---

## 📚 References and Prerequisites

### Recommended Books

- **C Programming**: _The C Programming Language_ by **Kernighan and Ritchie** (2nd Edition).
- **Assembly Programming**: _Intel Microprocessors Architecture and Programming_ by **Barry B. Brey** (any edition, e.g., 2nd or 8th).

### Prerequisites

- Solid understanding of **C programming**:
    - Functions, arrays, variables, etc.
- Familiarity with **assembly programming** for _any_ microprocessor (e.g., ARM).
- No prior knowledge of **Intel architecture** is required; Intel assembly instructions will be introduced as needed.

---

## 🗂️ Course Structure and Modules

### 📦 Module 1 (Week 1): Intel 8086 Basics

- Introduction to the **8086 processor architecture**
- Commonly used **assembly instructions**
- Usage of **stack instructions**
    
- Deep dive into **call** and **return** instructions
    

### 🧵 Module 2 (Week 2): Inline Assembly in C

- Syntax and use of **inline assembly** in C
    
- Mapping **C data types to low-level memory**
    
- Hands-on examples:
    
    - ALU operations
        
    - `strlen()` operation
        
    - Multiplication using repeated addition
        
    - **Swapping variables** in C and using inline assembly
        

### ⚙️ Module 3 (Week 3): Translating C to Assembly

- Focused on **function translation** into assembly
    
- Introduction to **function prologue and epilogue**
    
- Visual **animation** of memory segments:
    
    - Code segment
        
    - Data segment
        
    - Stack segment
        
- Study of **calling conventions** and **parameter passing**
    

### 🧭 Module 4 (Week 4): C vs C++ in Assembly

- Compare **structs in C** vs **classes in C++**
    
- Observe **access control** differences at assembly level
    
- Optimization using **hardware loops** for functions like:
    
    - `memcpy()`
        
    - `strlen()`
        
- Discuss converting **recursion into iteration** for better performance
    

---

## 🖥️ Microprocessor System Overview

### 📦 Microprocessor = "Black Box" for Computation

Connected to:

- **RAM** (Random Access Memory)
    
- Communicates via:
    
    - **Data Bus** (bidirectional)
        
    - **Address Bus** (unidirectional)
        
    - **Control Signals**: `RD` (read), `WR` (write)
        

### 📊 Logical Memory Map

- **Address Bus** = N bits → Can address `2^N` locations.
    
- **Each location** = K bits (commonly 8 bits per byte).
    

plaintext

CopyEdit

`Logical Map: +----------------+    Address 0 (8 bits) +----------------+    Address 1 (8 bits) ... +----------------+    Address 2^N - 1 (8 bits)`

- Logical addressing separates the **programmer's view** from the **physical memory layout**.
    

### 💡 Example

Even if **physically** each location is 16 or 32 bits wide, **logically** the memory is viewed as a sequence of **8-bit bytes**.

---

## 🧠 Key Takeaways

- The course will **bridge theory and hardware reality**.
    
- You'll learn how high-level code (C/C++) maps to **micro-level instructions**.
    
- Understanding memory access, the stack, and function internals is **key to mastering systems programming**.
    

---

## 📌 Next Steps

🔜 Begin **Module 1**:

- 8086 architecture
    
- Basic instructions
    
- Stack operations
    
- `CALL` and `RET` in assembly