### 🧠 **Memory Management in xv6 (for x86 Architecture)**

#### 🔁 **Memory Translation in x86:**

1. **Logical Address = Segment Selector + Offset**
2. **Segmentation Unit**: Converts **Logical Address → Linear Address**
3. **Paging Unit**: Converts **Linear Address → Physical Address**

---

### 🧩 **Segmentation in xv6:**

- **Segment Descriptor** (64-bit structure):
    - **Base Address** (32 bits split across 3 fields)
    - **Segment Limit** (20 bits split across 2 fields)
    - **Privilege Level (DPL)**: 0 (kernel) to 3 (user)
    - **Segment Type**: Executable (X), Readable (R), Writable (W)
- **xv6 uses only 4 segments**:
    - Kernel Code (X/R), DPL=0
    - Kernel Data (W), DPL=0
    - User Code (X/R), DPL=3
    - User Data (W), DPL=3
- **Defined in `mmu.h` using the `SEG` macro**
- Stored in **Global Descriptor Table (GDT)** using `struct segdesc gdt[]`
- GDT loaded via `lgdt()` function

---

### 📦 **Paging in xv6:**

#### 🗺️ Address Breakdown (Linear Address):

- 10 bits → Page Directory Index
- 10 bits → Page Table Index
- 12 bits → Offset within page

#### 🔧 xv6 Paging Setup:

- **CR3 Register**: Points to the Page Directory
- **Page Tables**: Dynamically created using:
    - `walkpgdir()` – builds page tables on demand
    - `mappages()` – sets up page mappings

#### 🌐 Kernel Mapping:

- Kernel space starts at `KERNBASE` (0x80000000)
- Identity mapping created:
    - **Virtual = Physical + KERNBASE**
    - **`V2P()`**: Virtual to Physical → subtract KERNBASE
    - **`P2V()`**: Physical to Virtual → add KERNBASE

#### 🗃️ Memory Regions (via `kmap[]` array):

1. **I/O Space**: Maps 0 → EXTMEM
2. **Kernel Text/Data**: Maps `KERNLINK` → physical extended memory
3. **Kernel Data & Free Memory**: Above Kernel code up to `PHYSTOP`
4. **Device Space**: At high physical addresses (near 0xFE000000)

---

### 🧾 **Memory Allocation in xv6:**

#### 📚 Free Page List (Linked List):

- All pages in free memory are 4KB
- Maintained via a **linked list using page memory itself**
    - 1st word in free page stores pointer to next free page
    - Head of the list is `freelist`

#### 🛠️ Functions:

- `kalloc()` – Allocates a free 4KB page (removes from list)
- `kfree()` – Frees a 4KB page (adds back to list)

---

### 📌 Summary:

- xv6 uses **minimal segmentation** and **two-level paging** (standard x86).
- Kernel is mapped to high memory via **identity + offset mapping**.
- **Page allocation is simple**, based on a **linked list of free pages**.
- While basic, this design mirrors many real-world OS concepts.

---