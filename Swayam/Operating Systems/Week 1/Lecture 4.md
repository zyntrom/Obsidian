## 🖥️ **Lecture Notes: Introduction to Processes & Operating System Structure**

---

### 📌 **1. From Program to Process**

- **Program**: A file stored on disk (e.g., `a.out`)—not yet executing.
- **Process**: A **program in execution**, loaded into RAM by the OS.

#### 🔁 Life Cycle:

1. **C code** → Compiled via `gcc hello.c` → `a.out`
2. **Execute via**: `./a.out`
3. OS loads `a.out` into RAM and starts a **process**.

---

### 📦 **2. Process Components**

Each process in memory contains:

- **Text**: Executable instructions (e.g., code for `main`, `fact` functions).
- **Data**: Global/static variables.
    - Split into **initialized** and **uninitialized** sections.
- **Heap**: Dynamically allocated memory (e.g., via `malloc()`).
- **Stack**: Local variables and function call info (e.g., recursion).
- **State** (hidden): Maintained by OS.
    - Contains registers, file descriptors, process ID, etc.

---

### 🧠 **3. Process Memory Layout**

#### ✅ Typical Layout:

```bash
Lower Address → 
Higher Address +-------------+ |   Text      | ← Code (Instructions) +-------------+ |   Data      | ← Global/static vars +-------------+ |   Heap      | ← malloc()/new |   (grows ↑) | +-------------+ |   Stack     | ← Local vars, function calls |   (grows ↓) | +-------------+
```

- Memory starts at address **0x0**.
    
- Ends at **MAX SIZE** (varies by OS).
    
    - Linux (32-bit): `0xC0000000`
        
    - xv6: `0x80000000`
        

---

### 🔒 **4. User Space vs Kernel Space**

- **User Space**: Memory from `0x0` up to `MAX SIZE`.
    
- **Kernel Space**: Above `MAX SIZE`, contains:
    
    - OS instructions and data
        
    - Kernel heap
        
    - Device memory (MMIO)
        
- User process **cannot** access kernel space directly.
    

---

### 👥 **5. Multiple Processes**

- Each process has:
    
    - Unique **user space** (text, data, heap, stack).
        
    - Shared **kernel mapping** (same for all processes).
        
- Enables **isolation** and **security**.
    

---

### 🧩 **6. System Calls**

- **System Call**: Controlled way for user programs to access OS services.
    
    - Ex: `write`, `read`, `open`, `close`, `fork`, `exec`, etc.
        
- Provides interface for:
    
    - File I/O
        
    - Memory allocation
        
    - Process creation
        
    - Hardware access
        

#### 🛠️ Example: `printf("hello")`

1. Calls C library function `printf()`.
    
2. Internally invokes `write()` system call.
    
3. **TRAP** instruction causes a **privilege switch** to **kernel mode**.
    
4. OS writes string to **stdout (screen)**.
    
5. Control returns to user space after completion.
    

---

### 🔄 **7. Function Call vs System Call**

|Aspect|Function Call|System Call|
|---|---|---|
|Instruction|`CALL`|`TRAP` / `int 0x80`|
|Privilege Level|User mode|Kernel mode (privileged)|
|Location of Code|User space|Kernel space|
|Destination Address|Variable (relocatable)|Fixed by hardware/OS|

---

### 📂 **8. File System Calls**

Examples of supported file operations:

- **Open a file**: `open()`
    
- **Read/Write**: `read()`, `write()`
    
- **Close a file**: `close()`
    
- **Change attributes**: `chmod()`, `utime()`
    
- Advanced: `seek()`, `link()`
    

#### OS Abstractions:

- OS hides hardware-level details (e.g., file on USB, HDD, CD-ROM).
    
- Only logical interface (file descriptor, path, etc.) exposed to user.
    

---

### 🧱 **9. Operating System Structure**

#### A. **Monolithic Kernel**

- All OS modules reside in a **single address space**.
    
- Modules (memory, files, networking, device drivers) can directly invoke each other.
    
- Examples: **Linux, xv6, MS-DOS**
    
- **Pros**:
    
    - Fast execution
        
    - Simple control flow
        
- **Cons**:
    
    - Large, complex codebase
        
    - Harder to maintain and secure
        

#### B. **Microkernel**

- Minimal kernel in kernel space.
    
- OS modules run as **separate user-space processes**.
    
- Use **IPC (Inter-Process Communication)** to interact.
    
- **Pros**:
    
    - Smaller trusted base
        
    - Better modularity and security
        
- **Cons**:
    
    - Slower due to IPC overhead
        
    - More complex messaging
        

---

### 📌 **10. Summary**

- A **process** is a running instance of a program in memory.
    
- OS maps code, data, heap, and stack into a memory layout per process.
    
- User processes use **system calls** to request services from the OS.
    
- The **monolithic** and **microkernel** designs represent two ends of OS architecture.