# 🧑‍💻 Lecture Notes – Simple C Program with Comments & Newline Characters

## 🧾 Objective

Learn how to:

- Trace the execution of a simple C program
- Use multiple `printf()` statements
- Write **comments**
- Use the **newline character `\n`** to improve program output formatting

---

## 🔄 Program Structure (Recap)

### Sample Code:

```c
#include <stdio.h>  
int main() {     
	printf("Welcome to\n");     
	printf("C programming\n");     
	return 0; 
}
```

### 📌 Breakdown:

|Line No.|Code|Purpose|
|---|---|---|
|1|`#include <stdio.h>`|Includes standard I/O library for `printf()`|
|3|`int main()`|Main function, execution starts here|
|4-5|`printf(...)`|Print output to terminal|
|6|`return 0;`|Ends the program successfully|

---

## 🧭 Program Execution Flow

1. Program starts with **line 3: `main()`**.
2. **Each line inside `main` executes in sequence.**
3. First `printf("Welcome to\n");` prints:  
    `Welcome to` → and moves the cursor to the next line.
4. Second `printf("C programming\n");` prints:  
    `C programming` → and moves the cursor to the next line again.
5. Execution ends when closing brace `}` is reached or on `return`.

> 🛠️ **Note**: The **newline character `\n`** ensures each message appears on a new line rather than running together.

---

## 🧩 Comments in C

### Syntax for Comments:

```c
/* This is a comment */
```

### 🔍 Characteristics:

- **Start**: `/*`
- **End**: `*/`
- Compiler **ignores comments**.
- Can be **single line** or **multi-line**.
- Used to explain:
    - Logic of code
    - Functionality
    - Section headers

> ✅ **Best Practice**: Always comment your code to improve **readability** and aid **team collaboration**.

### 📌 Example:

```c
/* This program demonstrates use of printf() */
```

---

## 🧵 More About `printf()` Function

### 🌟 `printf()` is a Library Function:
- Comes from the **standard I/O library (`stdio.h`)**
- Used for **output**
- Accepts a **string (in double quotes)** as its **argument**
- Anything between `" "` gets printed **as-is**

---

## 🔁 The Newline Character `\n`

### ✍️ Syntax:

```c
printf("Line1\nLine2\n");
```

### 🔍 What it Does:

- **`\n`** tells the terminal to:
    - End the current line
    - **Start a new one**

### 🧪 Example:

```c
printf("Welcome to\n\nC\n\nProgramming\n");
```

### 🧾 Output:

```
Welcome to  C  Programming
```

- **Multiple `\n` characters** create **blank lines** or **vertical spacing**

---

## ✅ Summary Checklist

|Concept|Key Points|
|---|---|
|`#include <stdio.h>`|Needed for input/output functions|
|`main()`|Program execution starts here|
|`printf()`|Used for printing messages|
|`;` (semicolon)|Ends every C statement|
|`{}` (curly braces)|Encloses body of function|
|`/* comment */`|Used to annotate code|
|`\n`|Newline character, creates line breaks|

---

## 🧪 Suggested Practice

Try editing your sample programs to:

1. **Remove** or **add** `\n` and observe output changes.
2. Add meaningful **comments** to each line of your code.
3. Experiment with multiple `\n` in a single `printf()`.
4. Trace execution line by line and predict output before running.