### **are Relationship**

- OS is in charge of managing the hardware.
- OS requires knowledge of underlying hardware to function properly.

---

### 💻 **2. Basic PC Hardware Structure**

- **CPU (Processor)**: Central component that interacts with various devices:
    - VGA card
    - Hard Disk
    - RAM
    - Keyboard
    - Mouse, etc.
- **Addressing**: Each device is assigned a **unique address range**.
    - Prevents conflict between devices.
    - Example: Hard disk responds to address `0x1F0 – 0x1F7`.

---

### 🧠 **3. Types of Addressing**

#### a. Memory Addressing

- Used for RAM.
- Each memory unit (byte/word) has a **unique address**.
- On **32-bit systems**, max addressable memory: `2³² = 4 GB`.
- **IBM PC RAM Map (legacy systems)**:
    - `0x00000 – 0x9FFFF` (up to 640 KB): Low memory (used by DOS).
    - `0xA0000 – 0xBFFFF`: VGA memory.
    - `0xC0000 – 0xEFFFF`: Expansion ROMs.
    - `0xF0000 – 0xFFFFF` (960 KB to 1 MB): BIOS.
    - `> 1 MB`: Extended memory (used by OS, applications, heap, stack).

#### b. IO Addressing (Legacy)

- **Separate 64 KB region** (`0x0000 – 0xFFFF`) for devices.
- Defined by **IBM PC Standard**:
    - Keyboard: `0x60 – 0x6F`
    - DMA Controller: `0xC0 – 0xDF`
    - Primary Hard Disk: `0x1F0 – 0x1F7`
    - PIC (Programmable Interrupt Controller): `0x20 – 0x3F`

#### c. Memory-Mapped IO

- Devices are mapped directly into **RAM address space**.
- Used due to **limited IO address space** (64 KB).
- Allows high-speed memory access to devices.

---

### 📏 **4. Device Address Standards**

- **IBM PC Standard**: Ensures hardware/software compatibility.
- **Plug and Play (PnP)**:
    - Devices are detected at boot.
    - BIOS allocates addresses dynamically.
    - Allocation is **not fixed** across reboots.

---

### 🧩 **5. Modern PC Architecture**

- **Processors**: Single or multi-core, multi-threaded.
- Connected via **Front Side Bus (FSB)**.
- **North Bridge**:
    - Connects CPU ↔ RAM (Memory Bus).
    - Connects CPU ↔ PCI (Peripheral Component Interconnect).
- **South Bridge**:
    - Handles legacy devices (PS/2 mouse, keyboard, PC speaker).
    - May connect via **DMI** (Direct Media Interface).
- **PCI Devices**: USB controller, Ethernet controller, etc., connected in **hierarchical trees**.

---

### 🧬 **6. Evolution of Intel x86 Architecture**

#### a. **Intel 8088 (1979)**

- 16-bit processor, 20-bit address bus.
- Max addressable memory: **1 MB (2²⁰)**.
- Segment:Offset memory addressing:
```
Physical Address = (Segment << 4) + Offset
```
- Registers (16-bit): AX, BX, CX, DX, BP, SP, SI, DI, CS, DS, ES, SS, IP.

#### b. **Intel 80386 (1985)**

- 32-bit processor, 32-bit address bus → **4 GB address space (2³²)**.
- Registers extended to 32-bit: **EAX, EBX, ECX, EDX, EBP, ESP, ESI, EDI**.
- Segment registers (CS, DS, etc.) remained 16-bit.
- Introduced **Protected Mode**, **Segmentation**, **Paging**.
- Maintains **backward compatibility** with 8086/8088.

#### c. **AMD K8 / x86-64 (2003)**

- 64-bit architecture.
- Registers extended to 64-bit: **RAX, RBX, RCX, etc.**
- Still maintains backward compatibility (8086 → 64-bit).
- Supports **larger memory** and more registers.

---

### 🎯 **Key Takeaways**

- Understanding hardware is essential to understanding how an OS works.
- Legacy standards (IBM PC) continue to influence modern system design.
- Memory management (via addresses) is foundational to device communication.
- The x86 architecture evolved while maintaining backward compatibility, enabling long-term software support.