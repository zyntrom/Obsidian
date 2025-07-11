## 🧠 Lesson Notes: Systematic Debugging – Detecting and Correcting Errors

**Course:** Problem Solving Using Programming  
**Module:** Getting Started with Problem Solving  
**Certified Score:** ✅ (Pending task)

---

### 🚨 Why Debugging and Formatting Matter

In **coding challenges and interviews**, your code’s output is **automatically checked** — which means:

- A single **extra space**, wrong **capital letter**, or incorrect **decimal precision** = ❌ failed test.
- You must match the **input and output format exactly** as shown.

---

### 🎯 Goal of the Lesson:

Learn to:

- **Take inputs** as specified
- **Print output** in **exact required format**
- Use **systematic debugging** to fix small, often overlooked issues

---

### 📥 Taking Specific Inputs

#### ✅ Python Example:

```python

#Integer 
input age = int(input("Enter your age: "))  
#String input name = input("Enter your name: ")  
print("Your name is:", name) 
print("Your age is:", age)

```

#### 🔍 Important Points:

- `int()` converts string input into an integer.
- `input()` always reads a string.
- If data types mismatch, errors will occur.
- Remember type casting (from previous lessons).

---

### 📤 Formatting Specific Outputs

#### ✅ Python Example (f-string and `.format()`):

```python
name = "Alice" 
age = 30  
#Using f-string 
print(f"Hello, my name is {name} and I am {age} years old.")  
#Using format method 
print("Hello, my name is {} and I am {} years old.".format(name, age))
```

#### ✅ C++ Example:

```c++
#include <iostream> 
#include <iomanip> 
using namespace std;  
int main() {     
float price = 25.5;     
cout << fixed << setprecision(2);     
cout << "Price: " << price << endl;  
// Output: Price: 25.50     
return 0; 
}``
```

---

### 💡 Special Formatting Case: Decimal Places

`price = 25.5 print(f"Price: {price:.2f}")  # Output: Price: 25.50`

- `.2f` means round and show **exactly 2 digits** after decimal.
- Used for prices, scores, measurements, etc.

---

### 🛠️ Debugging Tips

|Mistake|Fix|
|---|---|
|Wrong spacing/capitalization|Match sample exactly|
|Wrong number of decimals|Use `.2f` or `setprecision(2)`|
|Mixing data types (string/int)|Use `int()` or `str()`|
|Printing without format|Use `f-string` or `.format()`|

---

### 🧪 Task: Take Input and Output Formatted String

Write a program that:

- Takes:
    - An integer input for **age**
    - A string input for **name**
- Outputs:  
    `"Your name is <name> and you are <age> years old."`

#### ✅ Python Solution:

```python
name = input()
age = int(input()) 
print(f"Your name is {name} and you are {age} years old.")
```

#### ✅ C++ Solution:

```c++
#include <iostream> 
using namespace std;  
int main() {     
string name;     
int age;      
cin >> name;     
cin >> age;      
cout << "Your name is " << name << " and you are " << age << " years old." << endl;     
return 0; 
}
```

---

### 📌 Summary Table

| Concept             | Python                                          | C++                        |
| ------------------- | ----------------------------------------------- | -------------------------- |
| Input               | `input()`, `int()`                              | `cin >> variable;`         |
| Output              | `print()`, f-strings, `.format()`               | `cout << "text" << var;`   |
| Format Float        | `f"{x:.2f}"`                                    | `fixed`, `setprecision(2)` |
| Debug Format Errors | Match **spacing**, **case**, **decimal places** |                            |