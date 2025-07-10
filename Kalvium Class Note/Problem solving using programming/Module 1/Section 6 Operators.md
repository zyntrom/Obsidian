## 🧠 Problem Solving Using Programming — Lesson Notes

**Lesson Title:** _Operators_  
**Module:** Getting Started with Problem Solving  
**Certified Score:** ✅ 30/30

---

### 🔍 What Are Operators and Operands?

- **Operators**: Symbols like `+`, `-`, `==`, `>`, etc., used to perform actions on data.
    
- **Operands**: The values the operators work on.
    

**Example**:  
`5 + 3`

- `+` is the operator
    
- `5` and `3` are operands
    

---

### ❓ Why Are Operators Important?

- Operators let you **manipulate data**, **compare values**, and **make decisions**.
    
- Without them, code would just be static data with no intelligence or functionality.
    

---

## 🔧 Types of Operators

### 1. ✅ Arithmetic Operators

Used for basic math operations.

|Operator|Meaning|Example|Result|
|---|---|---|---|
|`+`|Addition|`5 + 2`|`7`|
|`-`|Subtraction|`5 - 2`|`3`|
|`*`|Multiplication|`5 * 2`|`10`|
|`/`|Division|`5 / 2`|`2.5`|
|`//`|Floor Division|`5 // 2`|`2`|
|`%`|Modulus (Remainder)|`5 % 2`|`1`|
|`**`|Exponentiation|`2 ** 3`|`8`|

**📌 Note:**  
In C++, `/` gives **integer division** if both operands are integers.

---

### 2. ✅ Relational / Comparison Operators

Used to compare two values and return a **boolean** (`True`/`False` in Python, `1`/`0` in C++).

|Operator|Meaning|Example|Result|
|---|---|---|---|
|`==`|Equal to|`5 == 5`|`True`|
|`!=`|Not equal to|`5 != 3`|`True`|
|`>`|Greater than|`5 > 3`|`True`|
|`<`|Less than|`5 < 3`|`False`|
|`>=`|Greater than or equal to|`5 >= 5`|`True`|
|`<=`|Less than or equal to|`5 <= 4`|`False`|

---

### 3. ✅ Assignment Operators

Assign values to variables and optionally combine with arithmetic.

|Operator|Meaning|Example|
|---|---|---|
|`=`|Assign|`x = 5`|
|`+=`|Add and assign|`x += 2` → `x = x + 2`|
|`-=`|Subtract and assign|`x -= 3`|
|`*=`|Multiply and assign|`x *= 4`|
|`/=`|Divide and assign|`x /= 2`|

📌 In **C++**, `/=` performs **integer division** if variables are integers.

---

### 4. ✅ Unary Operators

Work with **a single operand**.

|Operator|Meaning|Example|Result|
|---|---|---|---|
|`+`|Unary plus|`+a`|`a`|
|`-`|Unary minus (negate)|`-a`|`-a`|
|`++`|Increment (C++ only)|`++a`|`a+1`|
|`--`|Decrement (C++ only)|`--a`|`a-1`|

✅ Python supports only `+a` and `-a`.  
🚫 Python **does not support** `++a` or `--a`.

---

## 🧪 Quick Comparison Between Python & C++ Syntax

|Task|Python|C++|
|---|---|---|
|Add 2 numbers|`a + b`|`a + b`|
|Compare 2 values|`a > b`|`a > b`|
|Assign and add|`x += 2`|`x += 2;`|
|Increment value|`a = a + 1`|`a++;` or `++a;`|
|Decrement value|`a = a - 1`|`a--;` or `--a;`|

---

### 🎓 Summary

- **Arithmetic Operators** → Do math
    
- **Relational Operators** → Compare values
    
- **Assignment Operators** → Store & update variables
    
- **Unary Operators** → Modify single values (negate or increment)
    

---

### 📝 Sample Code (Python)

python

CopyEdit

`a = 10 b = 5  print(a + b)  # 15 print(a == b) # False a += 2        # a becomes 12 print(a)`

### 📝 Sample Code (C++)

cpp

CopyEdit

`#include <iostream> using namespace std;  int main() {     int a = 10, b = 5;     cout << (a + b) << endl;     cout << (a == b) << endl;     a += 2;     cout << a << endl;     return 0; }`

---

### 🌟 You’ve Learned:

✅ The symbols that make your code smart  
✅ How to do math, compare values, and update variables  
✅ Differences between Python and C++ operator behavior