## 🧠 Lesson Notes: Logical & Bitwise Operators

**Course:** Problem Solving Using Programming  
**Module:** Getting Started with Problem Solving  
**Lesson:** Logical & Bitwise Operators  
**Certified Score:** ✅ 30/30

---

### 🔹 What Are Logical Operators?

Logical operators help a program **make decisions** based on conditions that are either **True or False**.

#### ✅ Common Logical Operators:

|Operator|Meaning|Syntax (Python/C++)|Example|
|---|---|---|---|
|`and` / `&&`|Logical AND|`if a and b:`|Executes only if both conditions are True|
|`or` / `||`|Logical OR|
|`not` / `!`|Logical NOT|`if not a:`|Reverses the condition|

#### 🧪 Python Example:

```python
age = 25 
has_license = True  
if age >= 18 and has_license:     
print("Eligible to drive")  # ✅
```

---

### 🔹 What Are Bitwise Operators?

Bitwise operators act on **individual bits** (0 or 1) of integers, offering **low-level control** and fast operations.

#### 🧮 Key Bitwise Operators:

|Operator|Name|Description|Python / C++ Example|Result (a = 5, b = 3)|
|---|---|---|---|---|
|`&`|AND|1 if both bits are 1|`5 & 3` → `0001` → `1`|1|
|`|`|OR|1 if either bit is 1|`5|
|`^`|XOR|1 if bits are different|`5 ^ 3` → `0110` → `6`|6|
|`~`|NOT|Flip all bits|`~5` → `-6` (due to 2’s complement)|-6|
|`<<`|Left Shift|Shifts bits left (multiplies by 2)|`5 << 2` → `20`|20|
|`>>`|Right Shift|Shifts bits right (divides by 2)|`20 >> 2` → `5`|5|

#### 🧪 Python Example:

```python
a = 5  # 0101 
b = 3  # 0011  
print(a & b)  # 1 
print(a | b)  # 7 
print(a ^ b)  # 6 
print(~a)     # -6 
print(a << 2) # 20 
print(20 >> 2)# 5
```

---

### 🛠 Use Cases

#### ✅ Logical Operators:

- Validate login: `if user and password_correct`
- Check multiple conditions: `if score > 80 and attendance > 90`

#### ✅ Bitwise Operators:

- Embedded systems
- Permission flags (e.g., read/write/execute)
- Fast operations on large datasets

---

### 🔒 Real-World Example: File Permissions

```
READ = 4     # 100 
WRITE = 2    # 010 
EXECUTE = 1  # 001  
user_permissions = 5  # 101 → READ & EXECUTE  
if user_permissions & READ:     
print("Read access ✅") 
if user_permissions & WRITE:     
print("Write access ✅") 
else:     
print("No Write access ❌")
```

---

### 🔁 Bitwise Task: Swap Two Numbers Without a Temp Variable

#### ✅ Using XOR:

`a = 10` 
`b = 20`  
`a = a ^ b` 
`b = a ^ b` 
`a = a ^ b`  
`print("a:", a)  # 20` 
`print("b:", b)  # 10`

---

### ✨ Summary

|Concept|Use For|
|---|---|
|Logical Operators|Decision making using conditions|
|Bitwise Operators|Fast binary-level data manipulation|
|Combined Usage|Systems programming, hardware control|