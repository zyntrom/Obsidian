# 🗺️ Virtual Memory Mapping – From Virtual Address to RAM

## 🧾 Process Initialization

### 🔹 Compiling and Execution

- Compiling a program produces an executable (e.g., `a.out`).
- Executing `a.out` causes the OS to:
    - Create a **process**.
    - Assign a **virtual address space (VAS)**.

### 🔹 Virtual Address Space (VAS)

- Contiguous address space: starts from `0` → `MAX_SIZE`.
- `MAX_SIZE`: defined by OS (e.g., in **xv6**).
- VAS is **process-specific**.

### 🔹 Memory Segments in VAS:

|Segment|Description|
|---|---|
|**Text**|Contains executable code|
|**Data**|Global/static variables|
|**Heap**|Dynamic memory (`malloc`, etc.)|
|**Stack**|Function calls, local variables|

### 🔹 Source of Segment Info:

- All segment layout info is embedded in `a.out` by the **compiler and linker**.
- OS reads `a.out` to set up VAS on execution.

---

## 📍 Virtual Address Usage

- Every memory access (e.g., `printf("Hello World")`) uses a **virtual address**.
- Addresses like that of `"Hello World"` are **virtual**.

---

## 🔁 Virtual to Physical Address Translation

### 🔹 Key Hardware:

- **MMU (Memory Management Unit)** in the CPU handles translation.
- MMU reads virtual address → maps it to a **physical address**.

### 🔹 Key Software:

- **Operating System** creates the process **page table** in RAM.

---

## 📘 Page Table and Translation

### 🔹 Page Table:

- Maps **virtual pages** → **physical page frames**.
- Includes:
    - **Frame number**
    - **Present Bit (P-bit)**
    - **Dirty Bit (D-bit)**
    - **Protection Bits**

### 🔹 Page Table Pointer Register (PTPR):

- MMU uses **PTPR** to locate the process’s page table.
- Intel systems use **CR3 register** for PTPR.

---

## 🧮 Address Structure (32-bit Example)

### 🧷 Address Breakdown (for 4KB pages):

|Component|Bits|Purpose|
|---|---|---|
|Table Index|20|Index in the page table|
|Offset|12|Offset within a page|
|**Total**|32|Full virtual address|

- 12-bit offset → can address 2¹² = 4096 bytes = 4 KB page.
- 20-bit table index → 2²⁰ = 1M entries.
- If each entry is 4 bytes → page table = **4 MB** (must be contiguous).

---

## ❌ Problem: Page Table Must Be Contiguous

- **Issue**: 4 MB contiguous memory for each process’s page table may be hard to allocate.
- **Solution**: Use **Two-Level Paging**.

---

## 🧭 Two-Level Paging (Intel-style)

### 🔹 Address Breakdown (32-bit):

|Component|Bits|Description|
|---|---|---|
|Directory Index|10|Index into Page Dir|
|Table Index|10|Index into Page Table|
|Offset|12|Offset within page|

### 🔹 How It Works:

1. **CR3 (Page Directory Pointer Register)** → Points to **Page Directory** (4 KB).
2. **Directory Index (10 bits)** → Indexes into Page Directory → Points to **Page Table**.
3. **Table Index (10 bits)** → Indexes into the Page Table → Gives **Page Frame Number**.
4. **Offset (12 bits)** → Appended to form full **physical address**.
### ✅ Benefits:

- Each page table = **4 KB**, fits into a frame.
- Tables can be **non-contiguous** in RAM.

---

## 📜 Sequence of Virtual Memory Mapping (Runtime)

### 🔢 Step-by-Step Flow

1. **Program starts**: OS creates process, page table in RAM.
    - All **Present Bits = 0** initially (no blocks loaded).
2. OS begins execution at `main()`.
3. CPU issues **virtual address** for instruction in `main`.
4. MMU:
    - Reads CR3 (page directory pointer).
    - Tries to find page frame in the page table.
    - Sees **P-bit = 0** → **Page Fault** occurs.
5. **Page Fault Handling (by OS)**:
    - Validates if page access is legal.
    - Locates the block on disk (swap space).
    - Chooses a free/replaceable frame in RAM.
    - If dirty bit of replaced page = 1 → **Swap Out** old page.
    - **Swap In** the required page from disk (via **DMA**).
    - Updates page table:
        - Sets frame number
        - Sets Present Bit = 1
6. CPU retries instruction.
7. MMU now finds the physical frame → accesses **RAM**.
8. Instruction proceeds with data from correct physical address.

---

## 🤝 Participants in Virtual Memory System

|Component|Role|
|---|---|
|**OS**|Manages processes, page tables, handles faults|
|**CPU**|Executes instructions, sends virtual addresses|
|**MMU**|Translates virtual → physical, raises faults|

---

## 🧾 Summary of Key Concepts

|Term|Description|
|---|---|
|**VAS (Virtual Address Space)**|Each process has its own contiguous address space|
|**Page Table**|Maps virtual pages to physical frames|
|**CR3 / PTPR**|Register that stores pointer to page table (or page directory)|
|**MMU**|Hardware that translates virtual → physical addresses|
|**Page Fault**|Triggered when accessed page not in RAM|
|**DMA Transfer**|Used to copy page from disk to RAM|
|**Two-Level Paging**|Allows non-contiguous page table chunks|
|**Page Frame**|Fixed-size block of physical memory (usually 4 KB)|