## 🧠 Problem Solving Using Programming — Lesson Notes

**Lesson Title:** _Positional Extraction Techniques_  
**Module:** Getting Started with Problem Solving  
**Certified Score:** ✅ 30/30

---

### 📌 What is Positional Extraction?

**Definition:**  
Positional extraction means accessing a specific character (or element) in a sequence (like a string or list) using its **index (position)**.

Think of a string as boxes holding characters:

`Index:   0   1   2   3   4 String: 'H' 'e' 'l' 'l' 'o'`

To extract characters:

- First character → `string[0]` → `'H'`
- Third character → `string[2]` → `'l'`

---

### 🐍 Python Examples

```python
name = "Alice"  
print(name[0])   # A 
print(name[1])   # l 
print(name[4])   # e 
print(name[-1])  # e → last character using negative index
```

📌 **Note:**

- Indexing starts at `0`.
- `-1` gives the **last** character, `-2` gives the **second last**, and so on.
- Accessing an invalid index (like `name[10]`) gives `IndexError`.

---

### 💻 cpp Examples

```cpp
#include <iostream> 
#include <string> 
using namespace std;  
int main() {     
string name = "Alice";     
cout << name[0] << endl;  // A     
cout << name[1] << endl;  // l     
cout << name[4] << endl;  // e     
return 0; 
}
```

📌 **Note:**

- `string[index]` works like arrays.
- **Out-of-range** access (like `name[10]`) leads to **garbage value** or crash.

---

### 🛠️ Real-Life Applications of Positional Extraction

#### 1. ✅ Password Validation

**Use Case:** Check if a password starts with an uppercase letter.

```
password = "Abc123" 
if 'A' <= password[0] <= 'Z':     
	print("Starts with uppercase!")
```

#### 2. ✅ Extracting Initials from Full Name

Input: `"Abdul Pakir Jainulabdeen"`  
Output: `"A.P.J"`

```
name = "Abdul Pakir Jainulabdeen" 
parts = name.split() 
initials = ".".join([p[0] for p in parts]) 
print(initials + ".")  # A.P.J.
```

#### 3. ✅ Phone Number Check (Country Code)

```
phone = "+919876543210" 
if phone[:3] == "+91":     
	print("Indian number")
```

#### 4. ✅ File Type Detection from Extension

```
filename = "notes.pdf" 
if filename[-4:] == ".pdf":     
	print("Document file")
```

#### 5. ✅ Email Validation (presence of '@' and end with '.com')

```
email = "example@domain.com" 
if "@" in email and email.endswith(".com"):     
	print("Valid email")
```

---

### 🧪 Activity Preview

**Example Task:** Extract the **second-last digit** of a number.  
Technique: Convert to string → access `[-2]` index.

```python
num = 73542 
num_str = str(num) 
print(num_str[-2])  # 4
```

---

### ✨ Summary

| Concept        | Description                                                      |
| -------------- | ---------------------------------------------------------------- |
| Indexing       | Accessing items using position                                   |
| Starts at      | `0` (first character)                                            |
| Negative Index | `-1` = last, `-2` = second-last, etc.                            |
| Python         | Easy, readable string slicing                                    |
| cpp            | Behaves like arrays; `string[i]`                                 |
| Common Uses    | Initials, email/phone check, file type detection, password rules |
