## 🧮 Working With Digits – SPE 2025

**Why Learn This?**  
Digit-level operations are essential for:

- Counting digits
- Reversing numbers
- Finding sum/product of digits
- Detecting palindromes or Armstrong numbers
- Solving logic-based problems

---

### 🧰 Tools for Digit Extraction

|Operation|Purpose|Example|
|---|---|---|
|`%`|Gets the **last digit**|`123 % 10 = 3`|
|`//` (Python) / `/` (C++)|Removes the **last digit**|`123 // 10 = 12`|

> 🟡 Analogy: `%` gives the **last banana**, `//` or `/` removes it from the bunch 🍌

---

### 🧪 Example 1: Count the Number of Digits

#### ✅ Python Code:

```python
num = 12345 
count = 0 
while num > 0:  
	count += 1     
	num //= 10 
print("Total digits:", count)
```

#### ✅ C++ Code:

```C++
int num = 12345; 
int count = 0; 
while (num > 0) {     
	count++;     
	num /= 10; 
} 
cout << "Total digits: " << count;
```

#### 💡 Explanation:

Each loop iteration:

- Increases the count
- Removes the last digit using integer division

---

### 🔁 Loop Trace:

- 12345 → count = 1
- 1234 → count = 2
- 123 → count = 3
- 12 → count = 4
- 1 → count = 5
- Ends when num = 0

---

### 🧪 Example 2: Reverse a Number

#### ✅ Python Code:

```python
num = 1234 
rev = 0 
while num > 0:     
	digit = num % 10     
	rev = rev * 10 + digit     
	num //= 10 
print("Reversed:", rev)
```

#### ✅ C++ Code:

```c++
int num = 1234, rev = 0; 
while (num > 0) {     
	int digit = num % 10;     
	rev = rev * 10 + digit;     
	num /= 10; 
} 
cout << "Reversed: " << rev;
```

#### 💡 Explanation:

- `%` extracts the last digit
- `rev = rev * 10 + digit` builds the reversed number
- `/= 10` drops the last digit from the original number

---

### 🔄 Loop Trace:

- 1234 → rev = 4
- 123 → rev = 43
- 12 → rev = 432
- 1 → rev = 4321
- Done

---

### ⚠️ Common Mistakes:

- Forgetting to store the **original number** (if needed later)
- Using **floating point division** in Python (use `//` instead of `/`)
- Incorrect loop conditions (e.g., `while num != 0` may behave unexpectedly for negatives)

---

### 🧠 Summary

|Skill|Purpose|
|---|---|
|`% 10`|Extract last digit|
|`// 10` or `/= 10`|Remove last digit|
|Digit manipulation|Essential for number logic problems|