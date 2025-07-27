# 🧠 Module 2: Swapping Variables – C vs Assembly

---

## 🔄 Problem Overview

**Goal**: Swap two integer variables using different methods:

- Using a temporary variable in C
- Using the stack in assembly (without temp variable)
- As a function call (value vs reference)
- Using pointers and inline assembly

---

## 🧪 Method 1: C Swap Using Temporary Variable

### ✅ C Code:

```c
int x = 2, y = 3; 
int temp;  
temp = x; 
x = y; 
y = temp;
```

### 🛠️ Assembly Equivalent:

- Requires use of memory or registers
- Involves **multiple MOV instructions**
- Less efficient than stack-based version

---

## 🧪 Method 2: Assembly Swap Using Stack (Without `temp`)

### ✅ Concept:

Use `PUSH` and `POP` on the stack to reverse the values.

### ✅ Assembly Code:

```c
PUSH x    ; Push value of x onto stack 
PUSH y    ; Push value of y onto stack  
POP x     ; Top of stack (y) goes into x 
POP y     ; Next (original x) goes into y
```

### 🔍 Key Points:

- Uses **stack (LIFO)** to reverse values
- Does **not need any registers**
- May use same or more memory than temp-var version
- **More elegant** in inline assembly

---

## 📦 Summary: Comparing Methods

|Method|Memory Used|Simplicity|Register Use|Efficiency|
|---|---|---|---|---|
|C with temp variable|1 extra var|Easy|Yes|Moderate|
|Assembly with stack|2 stack entries|Simple ASM|No|Efficient|

---

## 🔄 Swapping in a Function

### ✅ C Function Attempt:

```c
void swap(int x, int y) {     int temp = x;     x = y;     y = temp; }
```

### ❌ Problem:

- Swaps **copies** of `x` and `y`
- **Does not affect original values** in `main`
- Prints before and after show same values

### 💡 Why?

- C **passes arguments by value** (not by reference)
- `swap(a, b)` passes _copies_ of `a` and `b`

---

## 🛠️ Solution: Use Pointers

### ✅ Updated Function:

```c
void swap(int *x, int *y) {     
	int temp = *x;     
	*x = *y;     
	*y = temp; 
}
```

Now `swap(&a, &b)` will correctly update `a` and `b`.

---

## 🔧 Attempt: Swap with Inline Assembly + Pointers

### ❌ Invalid Attempt:

```c
PUSH DWORD PTR [x] 
PUSH DWORD PTR [y] 
POP  DWORD PTR [x] 
POP  DWORD PTR [y]
```

### ❗ Why Not?

- Inline assembly **can’t directly dereference** pointers with `PUSH`/`POP` like this
- Must **load pointers into registers** first

---

## ✅ Correct Inline Assembly with Pointers

```c
MOV EAX, x       ; x points to address of a 
MOV EBX, y       ; y points to address of b  
MOV ECX, [EAX]   ; ECX = *x 
MOV EDX, [EBX]   ; EDX = *y  
MOV [EAX], EDX   ; *x = *y 
MOV [EBX], ECX   ; *y = *x
```

### 💡 Summary:

- Use `MOV` to **load and store** contents via pointers
- Registers like `EAX`, `EBX`, `ECX`, `EDX` used
- More control and precision in swap logic

---

## 🔍 Why the Stack Version Fails with Pointers

- `PUSH [x]` requires **direct memory access**
- But `x` is already a pointer — using `[x]` adds another level of indirection
- Inline assembly in C **cannot resolve [pointer-to-pointer]** without register involvement

---

## 💬 Final Thoughts

- Swapping is a great example to learn about:
    - Pass-by-value vs. pass-by-reference
    - Use of stack
    - Pointer arithmetic
    - Register/memory operations
- Sets the stage for **memory layout discussion** in Module 3