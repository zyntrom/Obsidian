# 🧑‍💻 Lecture Notes – Variables, Types, and Simple Arithmetic in C

## 🧾 Objective

Learn how to:
- Use variables in C
- Declare and assign values to variables
- Perform arithmetic operations
- Use format specifiers with `printf()`
- Understand variable naming rules and data types (`int`, `float`)
- Understand the difference between **assignment (=)** and **mathematical equality**

---

## 🧠 Concept of Variables

### 📦 Variables as Boxes:
- Think of variables as **named boxes** that hold values.
- Each box has:
    1. A **name**
    2. A **type** (e.g., `int`, `float`)
    3. A **value**

### 💡 Flowchart Parallel:

- In flowcharts: Variables are boxes that store temporary data during computation.
- In C: Variables are declared explicitly with types and used for computation/output.

---

## 🧪 Example Program: Celsius to Fahrenheit

### 🔢 Formula:

```
	F=(95×C)+32
```

### 🧰 Variables:

- `centigrade` → Celsius input
- `fahrenheit` → Fahrenheit result

### 🧾 Code:

```c
#include <stdio.h>  
int main() {     
	float centigrade;     
	float fahrenheit;      
	centigrade = 50;     
	fahrenheit = (9 * centigrade) / 5 + 32;      
	printf("The temperature ");     
	printf("%f Celsius = ", centigrade);     
	printf("%f Fahrenheit\n", fahrenheit);      
	return 0; 
}
```

---

## 🧩 New Concepts Introduced

### 1. 🧾 Variable Declaration

```c
float centigrade; 
float fahrenheit;
```

- Tells the compiler to:
    - Create memory space (boxes)
    - Allow only **real numbers** (floating point) to be stored
- `float` = type for **real numbers** (e.g., 12.3, 0.5, 122.0)

---

### 2. 🎯 Assignment Operation (=)

```
centigrade = 50; 
fahrenheit = (9 * centigrade) / 5 + 32;
```

- = means **copy value on right → to the variable on left**
- Not the same as **mathematical equality**
- Assignment is **directional**, not **symmetric**

📌 Example:

```c
b = 3; a = b; // a becomes 3, b remains 3
```

---

### 3. 🧮 Arithmetic Operators

|Operator|Symbol|Meaning|
|---|---|---|
|Multiply|`*`|Multiplication|
|Divide|`/`|Division|
|Add|`+`|Addition|

📝 Brackets `()` used to group expressions — same as in math.

---

### 4. 🖨️ `printf()` with Format Specifiers

#### 🔍 Example:

```c
printf("%f", centigrade);
```

- `%f`: Format specifier for **float** type
- Tells the program: _"Print the value stored in this float variable"_

📌 Key Points:
- First `printf()`: just a string
- Second `printf("%f", centigrade)`: has **2 parts**:
    1. **Format string**: `"%f"`
    2. **Variable**: `centigrade`

#### Sample Output:

```
The temperature 50.000000 Celsius = 122.000000 Fahrenheit
```

> 🛠️ Note: Default precision shows **6 decimal places** for floats.

---

## 🧪 What is a Float?

- `float` stands for **floating-point number**
- Used for **real numbers** (not just integers)
- Stored in computer memory with **limited precision**
- E.g., 50 → stored as 50.000000

---

## 🔣 Variable Naming Rules in C

✅ **Valid Names:**

- Use letters (A–Z, a–z), numbers (0–9), and underscores `_`
- Must **start with a letter or underscore**
- Can contain digits _after_ the first character

❌ **Invalid Examples:**

- `2centigrade` → ❌ (starts with number)

✅ **Valid Examples:**

- `centigrade`
- `centigrade1`
- `c_temp`
- `_fahrenheit`

🔍 **Case Sensitivity:**

- `Centigrade` ≠ `centigrade`
- C distinguishes between uppercase and lowercase

---

## 🔁 Types in C

### 1. `int` → Integer
- Whole numbers (e.g., 1, -5, 100)
### 2. `float` → Floating-point
- Real numbers with decimals (e.g., 3.14, -0.5)
### 🔐 Memory Limits:

- C uses **finite bits** to store variables
- E.g., on a 32-bit machine:
    - `int` range: approx −2,147,483,648 to +2,147,483,647
    - `float` range: large but finite (limited precision)

---

## ✅ Best Practices & Summary

|Concept|Best Practice|
|---|---|
|Variable Declaration|Always declare **before use**|
|Data Types|Match type to expected data|
|Naming|Use meaningful, lowercase names (e.g., `celsius`, `fahrenheit`)|
|Arithmetic|Use brackets for clarity|
|Output|Use `printf()` with correct format specifiers|
|Assignment|Remember `=` is not mathematical equality|

---

## 📌 Summary

- A **C program** to convert Celsius to Fahrenheit uses:
    - `float` variables
    - Basic arithmetic
    - `printf()` with format specifiers (`%f`)
- Understand **variable declarations, types, naming rules**
- **Assignment is one-way** (right → left)
- Always **declare variables before using them**