## 🖥️ **Operating System - Resource Management**

### 1. **Importance of Resource Management**

- Operating systems (OS) manage limited hardware resources.
- The **CPU** is the most critical and limited resource.
- Modern systems have multiple CPUs (e.g., 4, 8, 16 cores) vs. earlier systems with a single CPU.
- OS must ensure optimal CPU usage among competing applications.

---

### 2. **CPU Scheduling Strategies**

#### a. **Sequential Execution (Primitive OS like MS-DOS)**

- Runs one application until it finishes.
- Simple but inefficient: CPU remains idle during I/O waits (e.g., `scanf`).
- Results in poor CPU utilization.

#### b. **Multiprogramming**

- If an application blocks (e.g., waiting for input), the OS switches to another process.
- Applications resume from where they left off.
- Reduces idle CPU time, improves throughput.

#### c. **Multitasking (Time Sharing)**

- CPU time is divided into **time slices/quanta**.
- Each process gets a time slice to execute.
- Improves responsiveness and prevents one process from monopolizing the CPU.
- Creates illusion of concurrent execution.

---

### 3. **Multiprocessing and Parallelism**

- Systems may have **multiple processors (or cores)**.
- Allows **parallel execution** of applications on different processors.
- Each processor also uses time slicing.
- Improves performance and system throughput.

---

### 4. **Race Conditions and Synchronization**

- Occurs when multiple applications access a shared resource (e.g., file, printer) simultaneously.
- OS must **synchronize access** using **locks**:
    - Application locks resource before use.
    - Unlocks it after use.
    - Prevents concurrent access and data corruption.

---

### 5. **Process Scheduling**

- The **Scheduler** in OS decides:
    - Which process runs next.
    - Ensures **fairness** and **priority**.
- **High-priority tasks** (e.g., real-time sensors) get more CPU time.
- **Low-priority tasks** (e.g., compiling code) are delayed if needed.

---

### 6. **Isolation**

- Prevents interference between applications.
- Achieved via **privilege levels (rings)**:
    - **Ring 0**: Kernel mode (OS runs here).
    - **Ring 3**: User mode (applications run here).
- Applications cannot directly access hardware or each other’s data.
- Must go through **system calls** to access OS services.

---

### 7. **Security in Operating Systems**

#### a. **User Authentication**

- Usernames, passwords, biometrics (e.g., fingerprint scanning).
- Prevents unauthorized access.

#### b. **Access Control**

- Determines which user can access which file/resource.
- Example: Access Matrix:

|User|File1|File2|File3|Program1|
|---|---|---|---|---|
|Ann|R/W|R/W|None|Execute|
|Bob|R|None|R/W|None|
|Carl|None|R/W|None|Execute|

#### c. **Cryptography**

- Used for data protection, especially in communication and storage.

---

### 8. **System Security Evaluation**

- **Mathematical analysis** and **manual/semi-automated verification** used to assess security.
- Especially important in critical environments (military, defense).

---

## ✅ Summary

Operating systems play a **central role** in managing resources, especially the CPU, through techniques like **multitasking, multiprocessing, and synchronization**. They enforce **security and isolation** to protect users and system integrity. The **scheduler**, **privilege levels**, and **access controls** ensure fair and secure usage of system resources.