# 🧠 Memory Management – Segmentation & Paging (Intel x86)

## 🧩 What is Segmentation?

### 🔹 Definition

- Segmentation is a memory management scheme that divides a program into **logical modules**.
- Unlike paging (which splits memory into **fixed-size blocks**), segmentation creates **variable-sized segments** representing logical components of a program.

### 🔹 Logical Program Components (Segments):

- **Text** (code)
- **Data** (global/static variables)
- **Heap** (dynamic memory)
- **Stack**
- **Functions**, **Classes**, **Namespaces**, etc.

### ✅ Advantage over Paging:

- Maintains logical grouping; instructions of a function remain together.
- More intuitive and meaningful for programmers and compilers.

---

## 📍 Address Translation in Segmentation

### 🔢 Address Components

|Component|Description|
|---|---|
|**Segment Selector**|16-bit offset into Descriptor Table|
|**Offset Register**|32-bit address within the segment|
|**Logical Address**|`Segment Selector + Offset`|
|**Linear Address**|Calculated as `Base from Descriptor + Offset`|

### 🛠 Descriptor Table

- Stored in RAM
- Each row describes:
    - **Base Address** (start of segment in RAM)
    - **Limit** (size of segment)
    - **Access Rights** (R/W/X, privilege level, etc.)

### 🧮 Address Mapping Steps:

1. CPU generates **Logical Address**: `Segment Selector + Offset`
2. MMU uses:
    - **Pointer to Descriptor Table** (held in special register)
    - **Segment Selector**: index into descriptor table
3. Descriptor Table returns:
    - **Base Address**
    - **Limit**, **Access Rights**
4. Linear Address = `Base + Offset`

---

## 📦 Segment Descriptor Format (Intel x86)

### 🔹 Segment Descriptor Fields:

|Field|Description|
|---|---|
|**Base**|Starting physical address of segment (up to 4GB)|
|**Limit**|Maximum offset allowed|
|**Access Rights**|R/W/X permissions, privilege levels|

---

## 🖥 Registers in Segmentation (Intel 32-bit)

|Segment|Segment Selector|Offset Register|
|---|---|---|
|**Code**|`CS`|`EIP` (Instruction Pointer)|
|**Data**|`DS`, `ES`, `FS`, `GS`|Corresponding offset registers|
|**Stack**|`SS`|`ESP` (Stack Pointer)|

---

## 📂 Descriptor Tables in x86

### 🔹 Global Descriptor Table (GDT)

- Stored in memory
- Format: [Reserved | Segment Descriptors]
- Pointer held in **GDTR (Global Descriptor Table Register)**

#### 🧮 GDTR Format (48-bit):

|Bits|Purpose|
|---|---|
|Lower 16|Size of GDT|
|Upper 32|Base address (pointer to GDT)|

### 🔹 Local Descriptor Table (LDT)

- Similar to GDT but specific to a task/process (less commonly used)

---

## ❗ Fragmentation in Segmentation

### 🔹 Problem:

- **External fragmentation** occurs because segments vary in size.
- Example: 70 KB free total, but split into 60 KB + 10 KB → **can’t fit** a 65 KB segment.

### 🔹 Comparison:

|Scheme|Fragmentation Type|Severity|
|---|---|---|
|**Segmentation**|External Fragmentation|**High**|
|**Paging**|Internal Fragmentation|Low|

---

## 🔄 Combining Segmentation and Paging (Intel x86)

### 🧠 Why Combine?

- **Segmentation**: Logical program structure.
- **Paging**: Efficient physical memory use (avoids fragmentation).

### 🔢 Translation Workflow (x86):

1. CPU generates **Logical Address**:
    - `Segment Selector + Offset`
2. **Segmentation Unit**:
    - Converts to **Linear Address**
3. **Paging Unit**:
    - Maps **Linear Address → Physical Address**

---

## 🗺 Paging in x86 – 2-Level Translation

### 🔹 Linear Address Format (32-bit):

|Bits|Field|Purpose|
|---|---|---|
|10|Directory Index|Index into Page Directory|
|10|Table Index|Index into Page Table|
|12|Offset|Offset within page (4 KB)|

### 🔹 Key Components:

|Component|Purpose|
|---|---|
|**CR3 Register**|Points to Page Directory|
|**Page Directory**|Contains pointers to Page Tables|
|**Page Table**|Maps virtual pages to physical frames|
|**Offset**|Index into a 4 KB page|

### 📐 Example Workflow:

1. CPU → Logical Address (`CS:EIP`, etc.)
2. Segmentation Unit → **Linear Address**
3. Paging Unit:
    - Use **CR3** to get Page Directory
    - Use **Dir Index** → Page Table
    - Use **Table Index** → Frame Number
    - Append **Offset** → **Physical Address**

---

## ❓ Questions to Solve

1. **How many Page Tables can exist in a 32-bit Intel system?**
    - **Answer**:
        - 10-bit table index → `2^10 = 1024` page tables (each entry in the directory points to one page table)
2. **What is the maximum size of a process's address space?**
    - **Answer**:
        - 32-bit linear address → Max size = **4 GB**
        - Paging maps 4 GB linear space to physical memory

---

## 🔁 Full Address Translation Summary (x86)

|Stage|Input|Output|Component|
|---|---|---|---|
|**1**|Logical Address (`Segment + Offset`)|Linear Address|**Segmentation Unit**|
|**2**|Linear Address (`Dir + Table + Offset`)|Physical Address|**Paging Unit**|
|**3**|Physical Address|RAM Access|**Memory Subsystem**|

---

## 🧾 Summary Table: Segmentation vs Paging

|Feature|Segmentation|Paging|
|---|---|---|
|Split By|Logical Modules (functions, data, etc.)|Fixed-size Blocks (pages)|
|Address Type|Logical Address|Virtual Address|
|Fragmentation|**External (High)**|**Internal (Low)**|
|Ease of Mapping|Harder (variable size)|Easier (fixed size)|
|Intel x86 Usage|Creates Linear Address|Translates to Physical Address|