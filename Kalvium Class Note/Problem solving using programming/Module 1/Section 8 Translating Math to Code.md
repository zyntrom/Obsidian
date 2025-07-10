## 🧠 Problem Solving Using Programming — Lesson Notes

**Lesson Title:** _Translating Math to Code_  
**Module:** Getting Started with Problem Solving  
**Certified Score:** ✅ 30/30

---

### 🎯 Lesson Objective

Understand how to convert **mathematical formulas** and logic into **code instructions** in programming languages like Python and C++.

---

### 🧮 Relationship Between Math and Programming

|Math|Code|
|---|---|
|Uses formulas and variables|Uses variables and expressions|
|Solves problems step by step|Executes logic step by step|
|Uses symbols (like +, ×, ^)|Uses language-specific operators|
|Manual calculation|Automated calculation via code|

---

### 🤖 Analogy: Robot Delivery or Baking Assistant

- **Math** is the **recipe** or **blueprint**.
    
- **Code** is the **robot** or **machine** that executes it repeatedly, accurately, and instantly.
    

---

### ✅ Real-World Examples

#### 1. **Distance = Speed × Time**

**Python:**

python

CopyEdit

`speed = 60  # km/h time = 2    # hours distance = speed * time print(distance)  # 120`

**C++:**

cpp

CopyEdit

`int speed = 60; int time = 2; int distance = speed * time; cout << distance;  // 120`

---

#### 2. **Area of Circle = π × r²**

**Math Notation:**  
`Area = π × r²`

**Python:**

python

CopyEdit

`import math r = 5 area = math.pi * r ** 2 print(area)  # 78.53981633974483`

**C++:**

cpp

CopyEdit

`#include <iostream> #include <cmath> using namespace std;  int main() {     double r = 5;     double area = M_PI * pow(r, 2);     cout << area;  // 78.5398     return 0; }`

🧠 **Note:**

- Python uses `**` for power.
    
- C++ uses `pow()` and needs `<cmath>` header.
    
- C++ constant `M_PI` is defined in `cmath`.
    

---

### 🔄 Symbol Translation Summary

|Math Symbol|Python|C++|
|---|---|---|
|×|`*`|`*`|
|÷|`/`|`/`|
|^ (power)|`**`|`pow(base, exp)`|
|π (pi)|`math.pi`|`M_PI`|

---

### 🔁 Formula-to-Code Mindset

Whenever you see a formula:

1. Identify **inputs** (variables)
    
2. Determine **operations** (like multiply, square, add)
    
3. Translate using appropriate **syntax**
    

---

### 🧪 Example Problem Preview

Print the 5th multiple of a given number:

**Math:**  
`5th multiple = 5 × n`

**Python:**

python

CopyEdit

`n = int(input()) print(5 * n)`

---

### ✨ Summary

| Concept         | Explanation                                                  |
| --------------- | ------------------------------------------------------------ |
| Math → Code     | You convert a formula into a series of code instructions     |
| Programming     | Automates repetitive math operations                         |
| Language Syntax | Operators and functions vary slightly (e.g., `**` vs `pow`)  |
| Use Cases       | Distance, area, finance, scores, grades, anything math-based |