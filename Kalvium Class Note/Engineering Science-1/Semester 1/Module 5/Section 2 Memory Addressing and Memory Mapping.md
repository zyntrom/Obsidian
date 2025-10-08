## 🧠 Lesson 5.2 — Memory Addressing and Memory Mapping

### 🌟 Learning Objectives

By the end of this lesson, you should be able to:

1. Define **memory addresses** and their representation (binary/hex).
2. Understand and apply **addressing modes**: direct, indirect, immediate.
3. Explain the **address bus** and its role in memory access.
4. Illustrate **memory mapping** for CPU access to RAM and devices.
5. Compare **memory-mapped I/O** and **isolated I/O**, with pros and cons.
6. Understand **address decoding** in selecting memory or devices.
7. Solve **practical mapping problems** with specific address spaces.

---

## 🏢 Memory Addressing Concept

- Memory = massive apartment building → every location has a **unique address**.
- CPU uses these addresses to locate data quickly.
- Addresses are usually **binary** or **hexadecimal** (e.g., `0x1234ABCD`).
- Analogy: street address guides a visitor → memory address guides CPU.

---

## 🔍 Addressing Modes

|Mode|Description|Example|Pros/Cons|
|---|---|---|---|
|**Direct**|Instruction contains exact memory address.|`int y = x;`|Fast, but inflexible|
|**Indirect**|Instruction contains address of a location holding the actual address.|`int *ptr = &x; int y = *ptr;`|Flexible, address can change|
|**Immediate**|Instruction contains actual data.|`int x = 10;`|Very fast, only fixed values|

---

## 🛣️ Address Bus

- Pathway for addresses from CPU → memory.
- Width determines **memory capacity** (e.g., 32-bit bus → 4GB memory).
- Analogy: highway with more lanes → more memory can be accessed.
- CPU puts address on bus → memory controller fetches data.

---

## 🖥️ Memory Mapping

- CPU needs access to **RAM and devices** (e.g., GPU, ROM, network card).
- **Memory mapping** assigns blocks of addresses to devices → CPU treats devices like memory.
- Analogy: city address system covering houses, shops, offices.

### Memory-Mapped I/O vs. Isolated I/O

|Type|Description|Pros|Cons|
|---|---|---|---|
|**Memory-mapped I/O**|Device addresses integrated with memory addresses|Easy to program|Potential conflicts|
|**Isolated I/O**|Separate address space for devices|Reduces conflicts|Requires special instructions|
![[Pasted image 20251008163340.png]]
---

## 🏷️ Address Decoding

- Needed when **RAM and devices share address space**.
- Logic checks incoming address → decides which memory or device responds.
- Analogy: postal code ensures packages reach correct apartment.

---

## 🧮 Mapping Activity Example

**Computer with 64KB (65536 bytes) address space:**

|Device|Start Address|End Address|Size|
|---|---|---|---|
|RAM|0x0000|0x3FFF|16KB|
|ROM|0x4000|0x5FFF|8KB|
|Peripheral|0x6000|0x6FFF|4KB|

- Use addressing modes and decoding logic to identify which device responds to a CPU request.

---

## 🌐 Real-World Applications

1. **Operating Systems** – Virtual memory & mapping prevent apps from interfering with each other.
2. **Finance / Analytics** – High-speed memory mapping processes large datasets in milliseconds.
3. **Embedded Systems** – Microcontrollers read sensors / control devices using mapped memory.
4. **Graphics (GPU)** – Memory-mapped I/O enables smooth video and graphics performance.
5. **Network Routers / Hardware** – Mapping & decoding guides data accurately through complex systems.
![[Pasted image 20251008163350.png]]
---

## 🔑 Summary

- Memory addressing → uniquely identifies every data piece.
- Addressing modes → multiple ways for instructions to locate data.
- Address bus → pathway for CPU → memory/device.
- Memory mapping → unified CPU access to RAM + devices.
- Memory-mapped vs isolated I/O → programming trade-offs.
- Address decoding → selects correct memory/device in shared space.
- Critical for OS, device drivers, embedded systems, and efficient computing.

---

## 🎁 Bonus Content

- **Memory Mapping:** GeeksforGeeks
- **Memory-Mapped I/O vs Isolated I/O:** Baeldung
- **Memory Addressing Techniques:** YouTube
![[Pasted image 20251008163358.png]]