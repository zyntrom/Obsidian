## 🗓️ **Week 1 – Introduction to Operating Systems**

### 🎯 **Goal of the Week**

Lay the **foundation for all future weeks** by understanding:

- Where the OS fits in a computer system.
- What essential roles the OS plays.
- Why OS abstraction and resource management are necessary.

---

## 🧱 **Computer System as a Layered Architecture**

|Layer|Components|
|---|---|
|**1. Transistors (Base layer)**|CMOS Transistors|
|**2. Logic Gates**|AND, OR, XOR, Flip-Flops, Memory cells|
|**3. Hardware Units**|RAM, instruction decoder, ALU, etc.|
|**4. Operating System (OS)**|Manages hardware and software|
|**5. Applications**|Browsers, Office apps, Games, etc.|

---

## 🧠 **Two Major Roles of the Operating System**

### 1. 🧩 **Hardware Abstraction**

- Simplifies complex hardware operations into **easy-to-use interfaces** for applications.
- Example: `printf("Hello World")` is translated into a series of hardware operations:
    - Reads from memory
    - Sets coordinates, color, etc.
    - Writes to the **video buffer**
    - Instructs the **graphics card** to render the output

> ⚠️ Without OS, programmers would need to handle these hardware-specific details manually—making code complex, non-portable, and error-prone.

### 2. 🔄 **Resource Management**

- Shares limited hardware resources among multiple concurrent applications:
    - **CPU scheduling**
    - **Memory allocation**
    - **Device management**
- Ensures **isolation and protection** between applications:
    - One program cannot access data of another (e.g., banking app vs. a malicious game).

---

## 🧪 **Example: Why OS is Crucial – `printf("Hello World")`**

- Without OS:
    - Programmer must manually handle:
        - Memory address of string
        - Graphics buffer manipulation
        - Display attributes (color, position)
        - Hardware-specific behavior
- With OS:
    - Programmer writes one simple line
    - OS handles all complexities internally

✅ **Benefits of OS abstraction**:

- ✨ Simplicity
- 🔁 Reusability
- 🔄 Portability (code works across different hardware)

---

## ⚙️ **Why Resource Management Is Complex**

- Limited resources (e.g., 1–8 CPUs, 4–16 GB RAM)
- Many concurrent apps: browser, compiler, video call, etc.
- OS must:
    - Allocate resources fairly
    - Prevent one app from interfering with another
    - Maximize hardware utilization
    - Isolate sensitive apps (e.g., protect banking data from malware)

---

## 🔐 **Example: Need for Isolation**

- App 1: Banking website (entering credit card details)
- App 2: Infected game (malicious)
- ❌ Without OS isolation: Game could steal data
- ✅ With OS isolation: Apps are sandboxed; security is maintained

---

## 📱 **Types of Operating Systems**

|Type|Examples|Key Design Considerations|
|---|---|---|
|**Embedded OS**|Contiki|Low memory/power use (IoT)|
|**Mobile OS**|Android, iOS|Touch interface, power optimization|
|**Real-Time OS (RTOS)**|QNX, RTLinux|Hard timing guarantees|
|**Secure OS**|SeLinux, SeL4|Enhanced security for sensitive apps|
|**Desktop OS**|Windows, Mac, Ubuntu|User interaction, GUI, multitasking|
|**Server OS**|RedHat, Ubuntu Server|Reliability, scalability, remote access|

---

## 🛠️ **xv6 – The OS Used in This Course**

- **Developed by MIT** for educational use.
- **Small**, well-documented, and easy to study.
- Based on **UNIX Version 6 (V6)**.
- Learning xv6 gives deep insight into how **Linux-like systems** work internally.

---

## 🧾 **Key Takeaways from Week 1**

|Concept|Summary|
|---|---|
|**OS Role**|Abstract hardware & manage resources|
|**Abstraction**|Hides complexity of hardware (e.g., printf works on any machine)|
|**Resource Mgmt**|Shares limited CPU, memory, etc., while isolating processes|
|**Types of OS**|Tailored to device: mobile, real-time, secure, embedded, desktop|
|**Security**|OS prevents malicious apps from stealing data|
|**xv6 OS**|Teaching OS based on UNIX; used throughout course|