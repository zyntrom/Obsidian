# 📘 Notes: Add All Digits Until Result is Single Digit

### 🔹 Problem Statement

- You are given a number `num`.
- Task: Repeatedly **sum its digits** until the result has **only one digit**.
- Return this single-digit result.

---

### 🔹 Key Concepts

1. **Digit Extraction** → Use `% 10` to get last digit.
2. **Integer Division** → Use `// 10` or `/ 10` to remove last digit.
3. **Repeated Summation** → Continue summing digits until sum < 10.
4. **Mathematical Shortcut** → The final single-digit result is `num % 9` (except 0 → 0).

---

### 🔹 Step-by-Step Approach

1. Take input `num`.
2. While `num` has more than 1 digit:
    - Initialize `sum = 0`.
    - Extract each digit and add to `sum`.
    - Replace `num` with `sum`.
3. Print `num`.

---

### 🔹 Example Walkthrough

Input: `38`

- 38 → 3 + 8 = 11
- 11 → 1 + 1 = 2
- 2 → single digit → stop

Output: `2` ✅

---

# 🖥 Solutions

---

### ✅ Python

```python
num = int(input())

while num >= 10:
    total = 0
    while num > 0:
        total += num % 10
        num //= 10
    num = total

print(num)

```

---

### ✅ C++

```cpp
#include <iostream>
using namespace std;

int main() {
    int num;
    cin >> num;
    while (num >= 10) {
        int sum = 0;
        int temp = num;
        while (temp > 0) {
            sum += temp % 10;
            temp /= 10;
        }
        num = sum;
    }
    cout << num << endl;
    return 0;
}

```

---

### ✅ Java

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int num = sc.nextInt();
        while (num >= 10) {
            int sum = 0;
            int temp = num;
            while (temp > 0) {
                sum += temp % 10;
                temp /= 10;
            }
            num = sum;
        }
        System.out.println(num);
    }
}
```

---

✅ This is also called the **digital root** of a number.

- Shortcut (optional): `digital_root = 1 + (num - 1) % 9` (for num > 0).