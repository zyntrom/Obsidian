# 🧠 Microprocessor Abstraction & Register Architecture

---

## 📌 Recap

- Memory is modeled as a **black box**:
    - **Bidirectional Data Bus**
    - **Unidirectional Address Bus**
    - Controlled entirely by the **Microprocessor (µP)**
    - Commands used: `READ` and `WRITE`

---

## 🎯 Objective of the Microprocessor

- **Main Job**: Execute a program stored in memory between locations `X` and `Y`.
- Tasks performed:
    1. **Fetch**
    2. **Decode**
    3. **Execute**

This cycle is often written as:

```
F → D → E
```

---

## 🔁 Instruction Cycle (F-D-E)

- For `M` instructions between `X` and `Y`:
    
    `F1 D1 E1 F2 D2 E2 ... FM DM EM`
    
- Modern microprocessors use **pipelining**:
    
    - Parallelizes fetch, decode, and execute phases.
        
    - Increases **throughput** using **instruction prefetching**.
        

---

## 🧱 Registers Needed for Execution

### 🧭 Instruction Pointer (IP/EIP)

- Stores the **current instruction address**.
    
- For example:
    
    text
    
    CopyEdit
    
    `IP ← X  (Start of program)`
    
- After each execution, it's automatically incremented by the instruction's length `N`.
    

|Register|Width|Description|
|---|---|---|
|IP|16-bit|8086 Instruction Pointer|
|EIP|32-bit|Extended IP for x86 and above|

---

## ⚙️ Execution: ALU and Operands

### 🧮 Arithmetic Logic Unit (ALU)

- Requires **two operands**.
    
- Typically one operand is a **general-purpose register**.
    

---

## 📦 General Purpose Registers (GPRs)

Each has:

- A 16-bit form: e.g., `AX`
    
- 8-bit subparts: `AH` (high), `AL` (low)
    
- 32-bit extended form: `EAX`
    

|Register|8-bit High|8-bit Low|16-bit|32-bit|
|---|---|---|---|---|
|A|AH|AL|AX|EAX|
|B|BH|BL|BX|EBX|
|C|CH|CL|CX|ECX|
|D|DH|DL|DX|EDX|

> These are used for arithmetic, logic, and memory operations.

---

## 🪜 Stack Operations

### 🔂 Stack Registers

|Register|16-bit|32-bit|Purpose|
|---|---|---|---|
|SP|SP|ESP|Stack Pointer (Top of Stack)|
|BP|BP|EBP|Base Pointer (Frame Access)|

> LIFO memory structure used for:
> 
> - Function calls
>     
> - Local variable storage
>     

---

## 📏 String/Array Operations

### 🧮 Index Registers

|Register|16-bit|32-bit|Use|
|---|---|---|---|
|SI|SI|ESI|Source Index (Strings)|
|DI|DI|EDI|Destination Index (Strings)|

---

## 🧱 Segment Registers

Used to partition memory into logical segments:

|Register|16-bit|32-bit|Role|
|---|---|---|---|
|CS|CS|ECS|Code Segment|
|DS|DS|EDS|Data Segment|
|SS|SS|ESS|Stack Segment|
|ES|ES|EES|Extra Segment|

### 🔄 Address Construction

- Full address is **not** just EIP or ESP.
    
- Constructed as:
    
    text
    
    CopyEdit
    
    `Segment:Offset`
    
    Examples:
    
    - Code: `CS:EIP`
        
    - Stack: `SS:ESP` or `SS:EBP`
        
    - Data: `DS:EAX`, `DS:EBX`
        
    - Extra: `ES:EDI`
        

---

## 🚩 Flag Register (Status Flags)

Indicates the outcome of ALU operations:

|Flag|Description|
|---|---|
|Zero Flag (ZF)|Set if result is zero|
|Sign Flag (SF)|Set if result is negative|
|Carry Flag (CF)|Set if there's an arithmetic carry/borrow|
|Overflow (OF)|Set if signed overflow occurs|

> Flags are used in **conditional branching and loops**.

---

## 🧵 Summary

To execute the **Fetch-Decode-Execute (F-D-E)** cycle, a microprocessor needs:

- **Instruction Register (EIP)** – tracks current instruction.
    
- **General Purpose Registers** – store operands and results.
    
- **Stack Registers** – handle call stacks and function scopes.
    
- **Index Registers** – support string/array operations.
    
- **Segment Registers** – map logical segments to memory.
    
- **Flag Register** – enables decision-making in code.
    

---

## 🔜 Next Lecture

Will likely cover:

- **Move instructions**
    
- **ALU operations**
    
- **Practical register usage in C**