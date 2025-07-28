# 🧠 Memory Management in Operating Systems

## 📌 Overview

- **CPU** is the most important resource.
- **Memory (RAM)** is the second most critical **hardware resource**.
- The OS must **manage RAM** effectively to allow multiple processes to execute efficiently.

---

## 🧱 Basic Concepts

### 🟩 From Program to Process

- A **program** written in any language is **compiled** into an **Executable**.
- The **executable** is stored on the **hard disk**.
- When a user runs it:
    - The OS loads it into **RAM**.
    - It becomes a **process**.
    - The process then executes on the **CPU**.

### 🧩 Memory Map of a Process

- Stored in RAM:
    - **Text segment**: executable instructions
    - **Stack**: for function calls and local variables
    - **Heap**: for dynamic memory
    - **OS metadata**: registers, file handles, etc.

---

## 🧠 Importance of RAM

- RAM is **limited** (e.g., 4GB, 8GB, 16GB, 32GB).
- **Multiple processes** must coexist in RAM.
- OS must **manage memory maps** for all active processes.
- Either **parallel execution** or **time-sliced multitasking** is used.

---

## 🏗️ Memory Management Models

### 1️⃣ **Single Contiguous Model**

- **Oldest model** of memory management.
- Only **one process** is loaded in RAM at any time.
- After process completion, RAM is loaded with the next process.

#### ❌ Limitations:

- Sequential execution only.
- Process size must be ≤ RAM size.
- **Embedded systems** may have very small RAM (e.g., 12KB).
    - If process size is 100KB, it **cannot execute** on 12KB RAM.

---

### 2️⃣ **Partition Model**

- RAM is **divided into partitions** to support **multiple processes**.
- Processes are stored in **different partitions** in RAM.
- A **Partition Table** keeps track of:
    - **Base Address** of the process
    - **Size** of memory allocated
    - **Process ID**
    - **Usage flag** (free or used)

#### Example:

- Process A:
    - Base: 0x0, Size: 120KB
- Process B:
    - Base: 120K, Size: 60KB
- Free Block:
    - Base: 180K, Size: 30KB

#### Process Allocation:

- New Process (PID 5) needs 20KB.
    - OS finds the **30KB free block**, allocates 20KB.
    - Remaining 10KB marked as free.

#### Process Deallocation:

- If Process B completes:
    - 60KB becomes **free**.
    - Partition table updates this entry.
    - More processes can now be loaded.

---

## 🧨 Fragmentation

### ❗ Problem:

- Memory is **free but not contiguous**.
- Ex: 60KB (block 1) + 10KB (block 2) = 70KB total free memory.
    - A new process needs 65KB.
    - Cannot be loaded — memory is **fragmented**.
- Causes **underutilization** of RAM.

---

## ⚙️ Allocation Algorithms

### 1️⃣ **First Fit**

- Scans RAM from **top down**.
- Allocates process to the **first block large enough**.
- **Fast** but increases **fragmentation**:
    - Leaves behind **many small unusable chunks**.

### 2️⃣ **Best Fit**

- Scans **all free blocks**.
- Allocates process to the **smallest block that fits**.
- **Reduces fragmentation**, but:
    - **Slower** (requires checking all blocks).
    - Increases **OS overhead**.

---

## 🔄 Deallocation and Coalescing

- When a process ends:
    - Its memory block is **freed**.
    - OS checks **adjacent free blocks**.
    - **Merges** them into a **larger free block**.
- This helps reduce fragmentation and **supports larger processes** in the future.

---

## ⚠️ Limitations of Contiguous Models

|Issue|Description|
|---|---|
|**Fragmentation**|Memory split into small unusable chunks|
|**Fixed Allocation**|Entire process must be in **contiguous** RAM|
|**Size Limits**|Large processes can’t run if RAM is too small|
|**Performance**|Due to managing partitions and scanning|

---

## 🆕 Modern OS Memory Management

### ✅ Use:

- **Virtual Memory**
- **Segmentation**

→ Allows:

- **Non-contiguous allocation**
- **Larger programs to run**
- Better **memory utilization**

---

## 🔜 Next Topics

- Virtual Memory
- Segmentation
- Memory Management in Intel x86 processors