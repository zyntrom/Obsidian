# 🧠 Module 2: Optimized vs. Unoptimized Assembly from C Code

---

## 📌 Overview

- **Goal**: Understand how compilers translate C code into assembly and how optimization plays a key role.
- **Focus Areas**:
    - Arithmetic expressions involving division and remainder.
    - Redundant vs. minimal instruction generation.
    - Examples of both unoptimized and optimized translations.

---

## ⚙️ C Code to Assembly: Basic Division Example

### ✅ C Code:

```c
int x = 10, y = 20; 
int z, r;  z = x / y; r = x % y;
```

---

### 🧾 Unoptimized Assembly:

```c
MOV x, 0x000A     ; x = 10 
MOV y, 0x0014     ; y = 20  
MOV EAX, x 
IDIV y            ; EAX = x / y, EDX = x % y 
MOV z, EAX        ; store quotient  
MOV EAX, x        ; redundant: reload x 
IDIV y            ; repeat division 
MOV r, EDX        ; store remainder
```

### 🔍 Observations:

- **Two division operations** for quotient and remainder — **redundant**.
- Compiler does **not track** register contents between operations.

---

### ✅ Optimized Assembly:

```c
MOV x, 0x000A 
MOV y, 0x0014  
MOV EAX, x 
IDIV y 
MOV z, EAX 
MOV r, EDX
```

✔️ **Only one division**, both quotient and remainder used directly.  
✔️ This is what an **optimized compiler** would do.

---

## 🧩 Example 2: Chain of Arithmetic Operations

### ✅ C Code:

```c
int a, b, c, d; 
int x = 10, y = 5;  
a = x + y; 
b = a - y; 
c = b * y; 
d = c / y;
```

---

### 🧾 Unoptimized Assembly (Line-by-Line):

```c
MOV x, 0x000A 
MOV y, 0x0005    ; a = x + y 
MOV EAX, x 
ADD EAX, y 
MOV a, EAX       ; b = a - y 
MOV EBX, a       ; redundant 
SUB EBX, y 
MOV b, EBX  ; c = b * y 
MOV EAX, b       ; redundant 
IMUL y 
MOV c, EAX  ; d = c / y 
MOV EAX, c       ; redundant 
IDIV y 
MOV d, EAX
```

🔍 **Issues**:

- Registers like `EAX` are reloaded unnecessarily.
- MOV operations done even when the correct value is already in the register.
- Every step reinitializes values without considering the previous state.

---

### ✅ Optimized Assembly:

```c
MOV EAX, x 
ADD EAX, y       ; EAX = x + y 
MOV a, EAX       ; Save 'a'  
SUB EAX, y       ; EAX = a - y 
MOV b, EAX       ; Save 'b'  
IMUL y           ; EAX = b * y 
MOV c, EAX       ; Save 'c'  
IDIV y           ; EAX = c / y 
MOV d, EAX       ; Save 'd'
```

✔️ **No unnecessary MOVs**  
✔️ Registers reused wisely  
✔️ Only `EAX` used for most operations (since `EAX` is required for multiplication/division)

---

## ✅ Bonus: Adding Remainder Calculation

If you want both `d = c / y` and `e = c % y`, you can simply add:

```c
MOV e, EDX
```

Right after:

```c
IDIV y
```

Because:

- `EAX` stores **quotient**
- `EDX` stores **remainder**

---

## 🔑 Key Learnings

|Concept|Explanation|
|---|---|
|**Unoptimized Code**|Line-by-line conversion from C to assembly; no reuse of registers.|
|**Optimized Code**|Tracks register state, avoids redundant MOV/LOAD operations.|
|**DIV vs. IDIV**|`IDIV` is for signed integers (default in high-level languages like C).|
|**EAX, EDX Use**|`EAX` for quotient, `EDX` for remainder.|
|**Optimization Tools**|Compilers have optimization flags (e.g., `-O2`, `-O3` in GCC).|

---

## 💭 Final Notes

- Optimization significantly reduces the number of instructions.
- Reduces memory access and speeds up program execution.
- Understanding this helps in:
    - Writing better inline assembly
    - Reading compiler output
    - Debugging performance issues