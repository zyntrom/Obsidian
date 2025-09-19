# 📘 Notes: Minimum Sum of Four-Digit Number After Splitting Digits

### 🔹 Problem Statement

- Input: A **four-digit positive integer** `num`.
- Task: Split `num` into **two new integers** (`new1` and `new2`) using all digits exactly once.
- **Goal:** Find the **minimum sum** of `new1 + new2`.
- **Leading zeros are allowed**.

---

### 🔹 Key Concepts

1. **Extract Digits** → Separate the 4 digits from `num`.
2. **Sort Digits** → Sorting helps minimize sum by placing smaller digits at higher positions.
3. **Form Two Numbers** → Greedily assign digits alternately to `new1` and `new2` from sorted digits.
4. **Compute Sum** → Add `new1 + new2`.

---

### 🔹 Step-by-Step Approach

1. Read input `num`.
2. Extract each digit and store in a list/array.
3. Sort the digits in ascending order.
4. Form two numbers using **alternate digits** from the sorted list:
    - `new1 = first digit + third digit`
    - `new2 = second digit + fourth digit`
5. Sum the two numbers → this gives **minimum sum**.
6. Print the sum.

---

### 🔹 Example Walkthrough

Input: `2009`

- Extract digits → [2, 0, 0, 9]
- Sort → [0, 0, 2, 9]
- Assign alternately:
    - `new1 = 0*10 + 2 = 2`
    - `new2 = 0*10 + 9 = 9`
- Minimum sum = 2 + 9 = 11 ✅

---

# 🖥 Solutions

---

### ✅ Python

```python
num = input()
digits = sorted([int(d) for d in num])

new1 = digits[0]*10 + digits[2]
new2 = digits[1]*10 + digits[3]

print(new1 + new2)

```
---

### ✅ C++

```cpp
#include <iostream>
#include <algorithm>
using namespace std;

int main() {
    int num;
    cin >> num;
    int digits[4];
    for (int i = 3; i >= 0; --i) {
        digits[i] = num % 10;
        num /= 10;
    }
    sort(digits, digits + 4);
    int new1 = digits[0]*10 + digits[2];
    int new2 = digits[1]*10 + digits[3];
    cout << new1 + new2 << endl;
    return 0;
}

```

---

### ✅ Java

```
import java.util.Arrays;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String num = sc.next();
        int[] digits = new int[4];
        for (int i = 0; i < 4; i++) {
            digits[i] = num.charAt(i) - '0';
        }
        Arrays.sort(digits);
        int new1 = digits[0]*10 + digits[2];
        int new2 = digits[1]*10 + digits[3];
        System.out.println(new1 + new2);
    }
}

```

---

✅ **Explanation:**

- Sorting ensures smaller digits are at higher significance to minimize sum.
    
- Alternating assignment of digits forms the smallest possible sum.
    
- Works for any 4-digit number with leading zeros allowed.