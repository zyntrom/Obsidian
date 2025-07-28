# 🧠 Virtual Memory in Operating Systems

## 📌 Overview

- **Virtual Memory** is the **most commonly used memory management technique** in modern OS.
- Enables:
    - Non-contiguous memory allocation
    - Efficient RAM usage
    - Execution of programs larger than physical memory

---

## 🧱 Core Concepts

### 🔹 Page Frames

- RAM is divided into **equal-sized blocks** called **Page Frames**.
- Typical size: **4 KB** (may vary on modern CPUs).
- RAM example: 14 page frames (numbered 1 to 14).

### 🔹 Process Blocks (Pages)

- Process memory is also split into equal-sized **blocks**.
- **Block size = Page Frame size**.
- OS can map **any process block to any page frame**.

---

## 📋 Per-Process Page Table

### 🔹 Role:

- OS maintains a **page table for each process**.
- Maps **process blocks** to **RAM page frames**.

### 🔹 Example Mappings:

- Block 1 → Frame 14
- Block 2 → Frame 2
- Block 3 → Frame 13

→ Process blocks **need not be contiguous in RAM**.

---

## ⚙️ Address Translation

### 🔹 How it Works:

1. Process accesses a memory location.
2. **Memory Management Unit (MMU)**:
    - Looks up the **process's page table**.
    - Finds the corresponding **physical address** (frame).
3. RAM is accessed using the **physical address**.

### 🔹 Overhead:

- Page table lookup is required for **every memory access**.

### 🔹 Optimization:

- **TLB (Translation Lookaside Buffer)**:
    - A cache that **stores recent page table entries**.
    - Reduces lookup time.


---

## 🧍 Multiple Processes

- Each process has its **own page table**.
- Page tables are stored in **Kernel Space**.
    - Not accessible by user-space programs.
- Physical RAM is shared among processes:
    - Process 1 → Blue frames
    - Process 2 → Yellow frames
    - Process 3 → Orange frames

---

## 🔁 Context Switching

- At any time, **only one process executes** on CPU.
- During execution:
    - **That process’s page table is active**.
- During context switch:
    - Active page table is switched to the next process.
- **Isolation**:
    - Process 1 cannot access memory of Process 2 or 3.

---

## ❓ Do We Need to Load the Whole Process?

### ❌ No!

### 📍 Key Observation:

- **Locality of Reference**:
    - Programs access a **small portion of memory repeatedly**.
    - Many blocks may **never be accessed**.

---

## 📦 Demand Paging

### 🔹 Swap Space:

- A dedicated section of disk that stores **all process blocks**.
- Only **required blocks are loaded** into RAM **on demand**.

### 🔹 Page Fault:

- If a block is **not in RAM**, the **present bit = 0**.
- Accessing this block triggers a **Page Fault Interrupt**.

### 🔹 Page Fault Handling Steps:

1. MMU detects missing block (present bit = 0).
2. **OS handles the page fault**.
3. Loads required block from disk (swap) → RAM.
4. Updates page table:
    - Sets **Page Frame Number**
    - Sets **Present Bit = 1**

---

## 🔁 Page Replacement

### 🔹 Scenario:

- All page frames are full.
- A new block must be loaded → OS must **remove** an old block.

### 🔹 Decision:

- **Which page to remove?** → Decided by **Page Replacement Algorithms**

### 🔹 Common Algorithms:

|Algorithm|Description|
|---|---|
|**FIFO**|Remove the **oldest loaded** page|
|**LRU**|Remove the **Least Recently Used** page|
|**LFU**|Remove the **Least Frequently Used** page|

---

## 🔄 Swap In / Swap Out

|Term|Description|
|---|---|
|**Swap Out**|Move a page **from RAM → Disk**|
|**Swap In**|Move a page **from Disk → RAM**|

### 🔹 Dirty Bit (D-bit)

- **Indicates whether a page was modified in RAM.**
- D = 1 → Page is **modified** → Must **write back to disk** (Swap Out required).
- D = 0 → Page is **unchanged** → **No need to write back**.

---

## 🔐 Page Table Bits

### 🔹 Present Bit (P-bit)

- 1 = Page is in RAM
- 0 = Page is in disk → causes **Page Fault**

### 🔹 Dirty Bit (D-bit)

- 1 = Page was modified
- 0 = Page unchanged

### 🔹 Protection Bits

- Define **access rights**:
    - Executable
    - Read-only
    - Kernel vs. User mode

---

## 🧾 Summary

|Concept|Role|
|---|---|
|**Page Frame**|Equal-sized RAM units|
|**Page Table**|Maps process blocks to frames|
|**MMU**|Translates virtual to physical addresses|
|**TLB**|Caches recent translations|
|**Swap Space**|Disk area storing all process blocks|
|**Page Fault**|Occurs when accessing a non-resident page|
|**Page Replacement**|Chooses a page to remove from RAM|
|**Dirty Bit**|Indicates if a page was modified|
|**Protection Bits**|Control access rights to memory|