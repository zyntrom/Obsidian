## 🧠 Problem Solving Using Programming — Lesson Notes

**Lesson Title:** _Input and Output_  
**Module:** Getting Started with Problem Solving  
**Certified Score:** ✅ 30/30

---

### 🔍 Why Is Input and Output Important?

- Like a **vending machine**, your program needs input (user choice) and must return correct output (the snack).
- **Automated systems (judges)** test your code with strict input/output format rules.
- Even a **small mistake in formatting** (like a missing space or wrong word) can make your answer **fail** — even if your logic is perfect.

---

## 🔡 Input Statements

### ✅ Python

|Task|Code|
|---|---|
|📥 **Take string input**|`name = input("Enter your name: ")`|
|📥 **Take integer input**|`age = int(input("Enter your age: "))`|
|📥 **Take multiple inputs (space-separated)**|`x, y = input("Enter two numbers: ").split()`|
|🛠 Convert to integers|`x, y = map(int, input().split())`|

📌 **Important**: Everything from `input()` is a **string** by default.

---

### ✅ C++

|Task|Code|
|---|---|
|📥 **Take string input (one word)**|`cin >> name;`|
|📥 **Take integer input**|`cin >> age;`|
|📥 **Take multiple inputs**|`cin >> a >> b;`|
|📥 **Take full line (with spaces)**|`getline(cin, sentence);`|

📌 `cin` reads only until space. Use `getline()` to read full sentences.

---

## 🖨 Output Statements

### ✅ Python

|Task|Code|Output|
|---|---|---|
|Basic print|`print("Hello, world!")`|Hello, world!|
|With variable|`print("Hello,", name)`|Hello, Alice|
|Custom separator|`print("A", "B", sep="-")`|A-B|
|No newline|`print("Loading", end="...")`|Loading...|

### ✅ C++

|Task|Code|Output|
|---|---|---|
|Basic print|`cout << "Hello!" << endl;`|Hello!|
|With variable|`cout << "Hello, " << name << endl;`|Hello, Alice|
|Without newline|`cout << "A..."; cout << "Done!";`|A...Done!|

📌 C++ requires manual spaces using `" "`.

---

## 🧮 Printing with Precision

### ✅ C++ (Use `<iomanip>`)

```c++
#include <iomanip> 
cout << fixed << setprecision(2); 
cout << "Weight: " << weight << " kg";
```

### ✅ Python

```python
print(f"Weight: {weight:.2f} kg")
```

📌 `:.2f` → show float with 2 decimal places.

---

## 🔁 Escape Sequences

|Escape|Meaning|Example Output|
|---|---|---|
|`\n`|New line|Breaks into next line|
|`\t`|Tab space|Adds horizontal space|
|`\"`|Double quote|`\"text\"` → `"text"`|
|`\\`|Backslash|`\\` → `\`|

### Example:

`print("Name:\tJohn\nQuote: \"Practice makes perfect!\"")`

`cout << "Name:\tJohn\nQuote: \"Practice makes perfect!\"\n";`

---

## 🧪 Activity Summary

**🎯 Objective**:  
Read age (int) and full name (with space), and print in format:

> `Alice Johnson is 21 years old.`

### ✅ Python Code Example:

```python
age = int(input()) 
name = input() 
print(f"{name} is {age} years old.")
```

### ✅ C++ Code Example:

```c++
#include <iostream> 
#include <string> 
using namespace std;  
int main() {     
int age;     
string name;     
getline(cin, name);     
cin >> age;     
cout << name << " is " << age << " years old." << endl;     
return 0; 
}
```

---

## ✅ Key Takeaways

- **Input = user talks to the program.**
- **Output = program talks back.**
- **Formatting must be _exact_.**
- Always test with **expected input/output format** when submitting to coding platforms.