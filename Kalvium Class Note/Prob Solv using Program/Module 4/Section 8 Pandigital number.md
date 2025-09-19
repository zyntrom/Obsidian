## 🔹 Problem Restatement

We need to check if a number is **pandigital**.  
A number is pandigital if it contains **all digits from 1 to N exactly once**, where **N** is the number of digits in the number.

---

## 🔹 Step-by-Step Approach

1. **Extract digits manually**
    - Use modulo (`% 10`) to get the last digit.
    - Use integer division (`// 10`) to remove the last digit.
    - Store the digits.
2. **Count total digits (N)**
    - While extracting digits, count how many digits there are.
3. **Check conditions for pandigital**
    - All digits must be **between 1 and N**.
    - No digit should repeat.
    - The number must contain **all digits from 1 to N**.

---

## 🔹 Universal Python Code

```python
def is_pandigital(num):
    digits_seen = []
    count = 0
    temp = num
    # Extract digits one by one
    while temp > 0:
        digit = temp % 10
        digits_seen.append(digit)
        temp = temp // 10
        count += 1  # count total digits
    # Check if all digits are within 1..N
    for d in digits_seen:
        if d < 1 or d > count:
            return False
    # Check for uniqueness (no duplicates)
    if len(digits_seen) != len(set(digits_seen)):
        return False
    # Check if all digits from 1..N are present
    for i in range(1, count + 1):
        if i not in digits_seen:
            return False
    return True

# Input
num = int(input())

if is_pandigital(num):
    print("Yes")
else:
    print("No")

```

---

## C++ Program
## 🔹 Example Walkthrough

### Input:

```
54321
```
### Process:

- Extract digits → [1, 2, 3, 4, 5]
- Count = 5
- Check range → all digits are between 1 and 5 ✅
- Check duplicates → none ✅
- Check if all numbers from 1 to 5 exist → yes ✅

### Output:

```
Yes
```