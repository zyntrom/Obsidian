## 🧠 Module 2 Summary: Inline Assembly with C

### 🔧 Tool Introduction: **Compiler Explorer (Godbolt)**

- **Website:** https://godbolt.org
- **Purpose:** View real-time **C/C++ source code** and corresponding **assembly output**.
- **Interface:**
    - **Left pane:** Type or load your C code.
    - **Right pane:** Shows the **assembly output**.
    - Supports **multiple compilers**, including **MSVC**, **GCC**, and **Clang**.

---

## 🧱 Basic Setup

- Focus on:
    - **x86 architecture**
    - **MSVC compiler** (easiest for inline assembly)
- Assembly shown in color-coded format:
    - Each color corresponds to a C code block.
    - You can **hover over assembly instructions** to view explanations.

---

## 🧪 Example 1: Integer Division & Modulus

### C Code:

```c
int x = 10, y = 3, q, r; 
q = x / y; 
r = x % y;
```

### Key Concepts:

- Compiler throws error unless the function returns something (`div` must return a value).
- Assembly breakdown:
    - `mov x, 10`
    - `mov y, 3`
    - `mov eax, x`
    - `cdq` (sign-extends EAX into EDX:EAX)
    - `idiv y`
    - `mov q, eax` (quotient)
    - `mov r, edx` (remainder)

### Notes:

- `cdq`: Converts `EAX` into 64-bit signed value using `EDX:EAX` before division.
- Even **function braces** `{}` get translated into assembly (stack/frame setup).

---

## 🔧 Adding Inline Assembly

### Inline Assembly Example:

```c
asm("mov eax, q"); 
asm("mov ebx, r"); 
asm("imul ebx"); 
asm("mov m, eax");
```

- Inserts raw assembly inside C code.
- Must declare any used C variables before.
- Assembly is also **color-coded** in output for tracking.

---

## 🧠 Optimization and Compiler Behavior

### When **Optimization is ON:**

- Compiler **removes unnecessary operations**.
- Example:
```c
int x = 10, y = 4; 
return x % y;  // returns 2 directly
```
    - Constant folding: Evaluated at **compile time**.
    - Output is `mov eax, 2` → `ret`

### To prevent this:

- Pass `x`, `y` as **function parameters**, not constants.
    - Prevents compiler from precomputing.
    - Ensures division and remainder are done via assembly at runtime.

---

## 🔍 Optimized Division Example (With Function Args)

```c
int div(int x, int y) {     
	int q = x / y;     
	int r = x % y;     
	return q + r; 
}
```

- Assembly:
    - `mov eax, x`
    - `cdq`
    - `idiv y`
    - Result: `q = eax`, `r = edx`
    - `add eax, edx` (q + r)

---

## 🧪 Example 2: Pointer Arithmetic

### C Code:

```c
char *pA = 0; 
int *pB = 0; 
pA++; 
pB++;
```

### Assembly Output:

- `pA++` → `add eax, 1`
- `pB++` → `add ecx, 4`
- Why?
    - `char` = 1 byte
    - `int` = 4 bytes
- For:
    `short *pC = 0; pC++;`
    → `add edx, 2` (since `short` = 2 bytes)

---

## 🧪 Example 3: Custom strlen (String Length)

### C Code:

```c
char *pA = "This is a test string"; 
int i = 0; while (pA[i] != '\0') {    
	i++; 
} 
printf("%d", i);

```
### Assembly:

- Translated to **multiple lines of assembly**.
- Can be optimized with **inline assembly** for better performance.
- Include `#include <stdio.h>` to avoid `printf` error.

---

## 🔚 Final Example: Integer vs Floating Point Division

### Integer:

```c
int x = 10, y = 2; 
int q = x / y;  // → idiv in assembly
```

- `mov eax, x`
- `cdq`
- `idiv y`
- `mov q, eax`

### Floating Point:

```c
float q = 10.0 / y;
```

- Generates **completely different instructions**:
    - Uses SSE/XMM registers (`xmm0`, `xmm1`, etc.)
    - Offloaded to **coprocessor**

### Key Point:

- Stick to **integer operations** in this course.
- Floating-point adds unnecessary complexity for this level.

---

## ✅ Takeaways for Exam:

- Understand how **simple C operations** translate to **assembly**.
- Know how compiler optimization affects **generated code**.
- Be able to write and interpret **inline assembly** in C.
- Recognize **memory size impact** in pointer arithmetic.
- Identify when compiler uses `idiv`, `cdq`, or SSE for different data types.
- Use **Compiler Explorer** to experiment with code and understand low-level execution.