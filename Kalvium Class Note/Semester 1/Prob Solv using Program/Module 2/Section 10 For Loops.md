# 🌀 For Loops – Control Structures

## 🧠 What is a For Loop?

A **for loop** is a _control structure_ used to **repeat a block of code a specific number of times**.

### 🔍 When to Use a For Loop:

- You **know how many times** the loop needs to run.
- You want to **step through a range** of values.
- It helps avoid **repetition** and increases **efficiency**.

> 💡 Think of it as giving your computer clear instructions:  
> Start at 1 → Stop at 5 → Step by 1 → Repeat the task.

---

## 🧱 Structure of a For Loop

A **for loop** consists of **three parts**:
1. **Initialization** → Starting value
2. **Condition** → Runs loop _as long as this is true_
3. **Increment/Decrement** → Changes the loop variable after each iteration

---

## 🐍 For Loop in Python

**Syntax:**

```python
for i in range(1, 6):  
  print(i)
```

### 🔎 Explanation:

- `range(1, 6)` → Starts from 1, ends before 6 (i.e., up to 5)
- `i` is the loop counter
- `print(i)` runs for each value of `i` in the range

**Output:**  
1  
2  
3  
4  
5

---

## 💻 For Loop in cpp

**Code:**

```cpp
include <iostream>  
using namespace std;  
int main() {  
 for (int i = 1; i <= 5; i++) {  
  cout << i << endl;  
 }  
 return 0;  
}
```


### 🔎 Explanation:

- `int i = 1` → Initialization
- `i <= 5` → Loop runs while condition is true
- `i++` → Increments `i` after each loop
- `cout << i` → Prints each value of `i`

**Output:**  
1  
2  
3  
4  
5

---

## ✅ Advantages of For Loops

- Avoid **repeating code manually**
- Automate **repetitive tasks**
- Used for **number sequences**, **iterating through lists**, etc.
- Makes programs **cleaner, faster, and readable**

---

## 🧪 Practice Program – Print 1 to n in Reverse Order

### 🔤 Python Code:

```python
n = int(input("Enter a number: "))  
for i in range(n, 0, -1):  
	print(i)
```

### 💻 cpp Code:

```cpp
include <iostream>  
using namespace std;  
int main() {  
 int n;  
 cin >> n;  
 for (int i = n; i >= 1; i--) {  
  cout << i << endl;  
 }  
 return 0;  
}
```

---

## 🎯 Summary

- Use **for loops** when you know how many times to repeat.
- Efficiently handle repetition without writing code multiple times.
- Python uses `range()`, cpp uses a `(start; condition; step)` format.