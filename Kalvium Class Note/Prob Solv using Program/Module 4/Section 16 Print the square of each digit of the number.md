# 📘 Notes: Print the Square of Each Digit in Reverse Order

### 🔹 Problem Statement

- Input: A positive integer `num`.
- Task: Print the **square of each digit** in **reverse order**, separated by spaces.

---

### 🔹 Key Concepts

1. **Digit Extraction** → Use `num % 10` to get the last digit.
2. **Squaring Digits** → For each extracted digit, compute `digit^2`.
3. **Reverse Order** → Extract digits from last to first automatically gives reverse order.
4. **Looping** → Repeat until `num` becomes 0.

---

### 🔹 Step-by-Step Approach

1. Read integer `num`.
2. While `num > 0`:
    - Extract last digit → `digit = num % 10`.
    - Compute square → `digit^2`.
    - Print the square followed by a space.
    - Remove last digit → `num = num // 10`.
3. Stop when `num` becomes 0.

---

### 🔹 Example Walkthrough

Input: `13`

- Extract 3 → 3² = 9 → print 9
- Extract 1 → 1² = 1 → print 1

Output: `9 1` ✅

---

# 🖥 Solutions

---

### ✅ Python

```python
num = int(input())

while num > 0:
    digit = num % 10
    print(digit ** 2, end=" ")
    num //= 10
```

---

### ✅ C++

```cpp
#include <iostream>
using namespace std;

int main() {
    int num;
    cin >> num;
    while (num > 0) {
        int digit = num % 10;
        cout << (digit * digit) << " ";
        num /= 10;
    }
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
        while (num > 0) {
            int digit = num % 10;
            System.out.print(digit * digit + " ");
            num /= 10;
        }
    }
}

```

---

✅ **Explanation:**

- Extracting digits from right to left naturally reverses the order.
- Squaring is straightforward: `digit * digit`.
- Loop continues until all digits are processed.