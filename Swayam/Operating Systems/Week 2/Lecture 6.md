## 🖥️ How a PC Boots (Intel/AMD Platforms)

### 🔁 **Backward Compatibility in Intel CPUs**

- Intel CPUs retain backward compatibility with older CPUs like the 8086/386.
- Even modern i7 CPUs follow legacy steps during boot — processes from the 1990s still apply.

---

## ⚡ Step-by-Step Boot Process

### 1. **Power-On Reset (POR)**

- Triggered by pressing the **power/reset button**.
- Sends an **electrical pulse** to the CPU’s **reset pin**.
- On receiving this signal:
    - **All CPU registers = 0**, except:
        - **CS (Code Segment) = 0xF000**
        - **IP (Instruction Pointer) = 0xFFF0**
    - **Physical Address = 0xFFFF0**  
        (Calculated as `0xF000 << 4 + 0xFFF0`)

> 🔹 This address is 16 bytes below the **1MB mark** (0x100000), i.e., within the **BIOS ROM region**.

---

### 2. **Real Mode**

- CPU starts in **real mode**:
    - Max addressable memory = 1MB
    - No memory protection or privilege levels
    - Direct memory access allowed
- First instruction at **0xFFFF0** executes a **jump to BIOS code**.

---

### 3. **BIOS Execution**

- BIOS = Basic Input Output System
- Stored in **ROM/Flash (e.g., AMIBIOS)**, executes in real mode
- Tasks performed by BIOS:
    - **POST** (Power-On Self Test)
    - Initialize **video card**, devices
    - Display **BIOS splash screen**
    - Perform **memory test**
    - Configure **DRAM timing**
    - Setup **plug and play (PnP)** devices
    - Assign **IRQ**, **DMA** resources
    - **Identify Boot Device** (hard disk, USB, etc.)
    - Load **sector 0** (512 bytes) into **memory location 0x7C00**
    - **Jump to 0x7C00**

> 🔹 This 512-byte code is called the **MBR (Master Boot Record)**.

---

### 4. **MBR (Master Boot Record)**

- Loaded at **0x7C00**
- Contains:
    - **446 bytes** → bootloader code
    - **64 bytes** → partition table (4 × 16-byte entries)
    - **2 bytes** → boot signature (0x55AA)
- MBR code does:
    - Parses **partition table**
    - Loads **bootloader** of the selected OS

---

### 5. **Bootloader**

- Responsible for:
    - Presenting OS choices (optional)
    - Disabling interrupts
    - Setting up **GDT (Global Descriptor Table)**
    - Switching **real mode → protected mode**
    - Loading the **OS kernel** from disk to RAM

> 🔹 Protected mode = 32-bit, up to **4GB addressable memory**, supports memory protection

- Some systems **skip the MBR** and place the bootloader directly in sector 0

---

### 6. **Operating System Boot**

- After bootloader loads kernel:
    - OS takes over:
        - Sets up **virtual memory** (paging, page tables)
        - Initializes **interrupt vectors** and **IDT**
        - Initializes **hardware devices** (timer, console, disk, etc.)
        - Starts the **first user process**
        - Eventually starts the **shell**

---

## 🧠 Multiprocessor Boot (SMP Systems)

### **Symmetric Multiprocessing (SMP)**:

- All CPUs share:
    - **Memory (memory symmetry)**
    - **I/O devices (I/O symmetry)**

### **Processor Roles**:

- One CPU is the **Boot Strap Processor (BSP)**
- Others are **Application Processors (APs)**

### **Boot Steps**:

- BIOS runs only on **BSP**
- BSP:
    - Initializes hardware
    - Detects other processors (APs)
    - Sends **Startup IPI (Inter-Processor Interrupt)** to APs
- APs:
    - Skip hardware initialization
    - Start executing OS code

---

## ✅ Summary Flowchart:

```c
Power On → Reset Pulse → CPU starts at 0xFFFF0      
	↓ 
BIOS runs in Real Mode      
	↓ 
Loads MBR to 0x7C00 → Jumps to it      
	↓ 
MBR loads Bootloader      
	↓ 
Bootloader:    
	- Enters Protected Mode    
	- Loads OS kernel      
	↓ 
OS:    
	- Sets up memory, interrupts, devices    
	- Starts first user process → shell → user programs
```