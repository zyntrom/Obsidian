# Assembly

---

## 📌 Introduction

- **Goal**: Combine C programming with assembly instructions using _inline assembly_.
- Inline assembly allows embedding low-level assembly instructions directly inside a C program.
- **Assumption**: The learner already knows basic C programming and x86 assembly (from Module 1).

---

## 💡 What is Inline Assembly?

- Inline assembly allows you to:
    - Insert **assembly instructions** into a **C function**.
    - Use **C variables** inside assembly code.
- Syntax depends on the compiler; here, we use:
    - **Microsoft Visual C (MSVC)** for its easier syntax.

---

## 🧩 Why Inline Assembly?

- To **speed up specific operations**.
- To gain **low-level control** while maintaining C code structure.
- To **optimize** performance-critical sections.

---

## 🧪 Simple Inline Assembly Example

### C Code Snippet:

```c
void main() {     
	int x = 2;     
	x = x + 2;     
	printf("%d\n", x); 
}
```

### Converted with Inline Assembly:

```c
void main() {     
	int x = 2;     
	__asm {         
		mov EAX, x     ; Load x into EAX         
		add EAX, 2     ; EAX = EAX + 2         
		mov x, EAX     ; Store result back in x     
	}     
	printf("%d\n", x);  // Output: 4 
}
```

✅ Inline assembly handles only a part of the logic (`x = x + 2`).

---

## 🧮 Data Types & Sizes (C and Assembly)

|C Type|Size|Equivalent (x86)|
|---|---|---|
|`char`|1 byte|Byte|
|`short`|2 bytes|Word|
|`int`|2 or 4 bytes|Word or Double Word|
|`long`|4 bytes|Double Word (DWORD)|

- Depends on **compiler** and **architecture**.
- Maps to how registers (like AX, EAX) handle data.

---

## 🧾 Example 1: Arithmetic & Logical Operations

### Objective:

Evaluate:

- `EAX = x * y + a - b`
- `EBX = x ^ y | (a & b)`  
    (_All variables are 32-bit integers_)

### Code:

```c
int x = 2, y = 3, a = 4, b = 5;  
__asm {     
	mov EAX, x     ; EAX = x     
	mul y          ; EAX = EAX * y (EDX:EAX = result)     
	add EAX, a     ; EAX += a     
	sub EAX, b     ; EAX -= b 
}  
__asm {     
	mov EBX, x     ; EBX = x     
	xor EBX, y     ; EBX ^= y     
	mov ECX, a     ; ECX = a     
	and ECX, b     ; ECX = a & b     
	or EBX, ECX    ; EBX |= ECX 
}
```

- `EAX` stores `x * y + a - b`
- `EBX` stores `x ^ y | (a & b)`

---

## 🔁 Example 2: Using Loops in Assembly

### Objective:

Compute `z = x * y` using **repeated addition** instead of `mul`.

### Code:

```c
int x = 2, y = 3, z = 0;  
__asm {     
	xor EAX, EAX     ; EAX = 0 (accumulator)     
	mov ECX, y       ; ECX = counter (y)  
MULT:     
	add EAX, x       ; EAX += x     
	dec ECX          ; ECX--     
	jnz MULT         ; If ECX != 0, jump to MULT      
	mov z, EAX       ; z = result in EAX 
}  
printf("%d\n", z);  // Output: 6
```

✔ Shows how to:

- Use `jnz` (Jump if Not Zero)
- Simulate multiplication via addition
- Use labels like `MULT` for loops

---

## 🔑 Summary of Instructions Used

|Instruction|Description|
|---|---|
|`mov`|Move data between registers/vars|
|`add`|Addition|
|`sub`|Subtraction|
|`mul`|Unsigned multiply (EAX is implicit)|
|`xor`|Bitwise XOR|
|`and`|Bitwise AND|
|`or`|Bitwise OR|
|`dec`|Decrement by 1|
|`jnz`|Jump if not zero|
|`label:`|Label for jumping/branching|

---

## 🧠 Concepts Reinforced

- Accessing and using **C variables** in inline assembly
- Using **assembly registers** for arithmetic and logic
- Understanding how **data types** map between C and assembly
- Implementing **loops and branching** in assembly

---