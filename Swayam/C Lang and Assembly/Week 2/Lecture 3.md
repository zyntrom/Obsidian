# 🧠 Module 2: Pointer Arithmetic & String Length in Assembly

---

## 📌 Pointer Arithmetic in C vs. Assembly

### C Example:

```c
char *pA = 0; 
int  *pB = 0;  
pA++;   // increments by 1 pB++;   // increments by 4
```

### 🔍 Why?

- `pA++`: Adds **1** because `char` is **1 byte**.
- `pB++`: Adds **4** because `int` is **4 bytes**.

### Assembly Translation:

```c
MOV pA, 0x00000000 
MOV pB, 0x00000000  
; pA++ 
MOV EAX, pA 
ADD EAX, 1           ; char = 1 byte 
MOV pA, EAX  
; pB++ 
MOV EBX, pB 
ADD EBX, 4           ; int = 4 bytes 
MOV pB, EBX
```

✅ **Pointer arithmetic** depends on the **data type size** being pointed to.

---

## 📏 Calculating String Length in Assembly

### 🎯 Goal:

Implement the equivalent of `strlen()` using inline assembly.

---

### ✅ C Implementation (Simplified):

```c
char *pA = "THIS IS"; 
int count = 0;  
while (pA[i] != '\0') {     
	i++;     
	count++; 
} 
// Or simply: 
while (*pA++ != '\0') {     
	count++; 
}
```

---

### 🔧 Assembly Implementation (Optimized Inline Version)

#### 🔹 Setup:

```c
MOV ECX, 0        ; ECX = count (initialize to 0) 
MOV EBX, pA       ; EBX points to string start
```

#### 🔹 Loop:

```c
SCAN: 
CMP BYTE PTR [EBX], 0     ; Check if character is '\0' 
JZ DONE                   ; If so, we're done 
INC ECX                   ; Increment count 
INC EBX                   ; Move to next character (char = 1 byte) 
JMP SCAN                  ; Repeat loop
```

#### 🔹 Exit:

```c
DONE: 
MOV count, ECX
```

---

## 🧩 Notes on Instruction Semantics

|Instruction|Meaning|
|---|---|
|`CMP BYTE PTR [EBX], 0`|Compare current character with null terminator|
|`JZ DONE`|Jump if zero flag is set (i.e., character == '\0')|
|`INC ECX`|Increment character count|
|`INC EBX`|Move pointer to next character|
|`ADD EBX, n` (if `int *pB`)|Use instead of `INC` for types larger than 1 byte|
|`BYTE PTR`, `WORD PTR`, etc.|Indicate operand size: 1/2/4 bytes respectively|

---

## 🧠 Important Concepts

- **Pointer arithmetic** is data-type dependent.
- Assembly code must explicitly account for **data sizes**.
- `INC` is fine for single-byte data like `char`, but for `int`, use `ADD EBX, 4`.
- `BYTE PTR` tells the CPU how many bytes to access during compare or move operations.
- Avoid redundant registers (like using both `i` and `count`); optimize for performance.

---

## ✅ Final Assembly Summary for `strlen` Logic

```c
MOV ECX, 0         ; ECX = count 
MOV EBX, pA        ; EBX points to string  

SCAN: 
CMP BYTE PTR [EBX], 0 
JZ DONE 4
INC ECX 
INC EBX 
JMP SCAN  
DONE: 
MOV count, ECX
```