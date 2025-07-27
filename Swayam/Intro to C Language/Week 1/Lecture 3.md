# 🧑‍💻 Lecture Notes: The Programming Cycle & Writing Your First C Program

**NPTEL Introductory Programming in C – Lecture 3**

---

## 🎯 Learning Objectives

- Understand the **programming cycle** (Edit → Compile → Run)
- Learn what a **compiler** does and why it is necessary
- Write and compile your **first C program**
- Recognize **common syntax errors** in C

---

## 🔁 The Programming Cycle: Edit – Compile – Run

### 1. **Edit**

- Use a **text editor** to write your C program.
- Editors let you create, modify, and save text files (e.g., `.c` files).
- Examples:
    - **Linux**: `gedit`, `nano`, `vim`
    - **Windows**: `Notepad++` (not regular Notepad)

> 🔹 Save your file with a `.c` extension.  
> 🔹 Example: `sample.c`

---

### 2. **Compile**

- The computer **cannot understand C code directly**.
- You need to **translate** it into machine code using a **compiler**.
- This translation process is called **compilation**.

### 📌 Why Compilation Is Needed

- Example:  
    C statement:
    
    `g = a % b;`
    
    - `%` is the **modulo operator** (remainder after division).
- Microprocessors **don’t understand** this directly.
- The compiler translates it into:
    - Load data from memory
    - Perform division
    - Store remainder
    - Save result to memory

### 🧱 Compilation vs. Machine Code

- Writing directly in machine/assembly language is:
    - Tedious
    - Error-prone
    - Non-portable (CPU-dependent)
- C code is:
    - Shorter
    - Easier to read
    - **Portable** (can run on multiple systems with appropriate compiler)

### 🛠 Compiler = Translator

- Input: C code
- Output: Machine code (executable file)

### 🔧 Compilation on Linux (using GCC)

- Command:
```
    gcc sample.c
```
    
- If successful:
    - No message (silent success)
    - A new file is created: `a.out`
- If errors exist:
    - Error messages are printed
    - No executable is created
    - You must go back to editing and fix the issues

---

### 3. **Run**

- After successful compilation:
    
    - Run the program using:
        
        bash
        
        CopyEdit
        
        `./a.out`
        
- The output will be printed in the terminal.
    

---

## 👨‍💻 Writing Your First C Program

### 📝 Sample Program (sample.c)

c

CopyEdit

`#include <stdio.h>  int main() {     printf("Welcome to C\n");     return 0; }`

---

### 🔍 Code Breakdown

|Line|Code|Purpose|
|---|---|---|
|1|`#include <stdio.h>`|Includes the **Standard Input Output** library|
|2|`int main()`|Entry point of every C program|
|3|`{`|Begin of main function block|
|4|`printf("Welcome to C\n");`|Prints a message to terminal|
|5|`return 0;`|Indicates successful program termination|
|6|`}`|End of main function block|

---

### 💡 Important C Syntax to Remember

|Element|Description|
|---|---|
|`#include <...>`|Preprocessor directive to include libraries|
|`main()`|Starting point of the program|
|`{ ... }`|Defines the block of code|
|`printf(...)`|Function to print output|
|`;`|Every statement ends with a semicolon|
|`"..."`|Strings must be enclosed in double quotes|
|`\n`|Newline character (moves to next line)|

---

## ⚠️ Common C Programming Errors (Even in Simple Code)

|Error Type|Description/Example|
|---|---|
|Missing `#include <stdio.h>`|Compile error: undefined reference to `printf`|
|Missing `main()` function|Compile error: no entry point|
|Missing semicolon|Syntax error: "expected `;` before..."|
|Missing quotes in `printf`|Syntax error: string not terminated|
|Missing `{` or `}`|Syntax error: block not closed|

> ✅ **Tip**: Try deliberately introducing these mistakes and observe the compiler's error messages. It will help you debug better in future.

---

## ✅ Summary

|Step|Action|
|---|---|
|**Edit**|Write code in a text editor|
|**Compile**|Use a compiler (`gcc sample.c`)|
|**Run**|Execute with `./a.out`|
|**Fix Errors**|Read error messages, edit, and recompile|

---

## 🔄 Full Cycle Example

plaintext

CopyEdit

``1. Write code in `sample.c` 2. Compile:   gcc sample.c 3. Run:       ./a.out 4. Output:    Welcome to C``