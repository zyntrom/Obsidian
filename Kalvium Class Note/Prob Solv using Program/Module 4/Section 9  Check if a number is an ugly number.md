# 📝 Notes on Ugly Numbers

## 🔹 Definition

- An **ugly number** is a **positive integer** whose **prime factors** are only `2`, `3`, or `5`.
- By definition, `1` is also an ugly number.

---

## 🔹 Examples

- **Ugly numbers**: `1, 2, 3, 4, 5, 6, 8, 9, 10, 12…`
- **Not ugly numbers**: `7, 11, 13, 14…` (because they have prime factors other than `2, 3, 5`).

---

## 🔹 Key Properties

1. Divide the number repeatedly by `2`, `3`, and `5`.
2. If the number becomes `1`, then it is **ugly**.
3. If it reduces to any other number > 1, then it is **not ugly**.
4. Ugly numbers are always **positive**.

---

## 🔹 Algorithm (Step-by-Step)

1. If the number ≤ 0 → **not ugly**.
2. While divisible by `2`, divide it by `2`.
3. While divisible by `3`, divide it by `3`.
4. While divisible by `5`, divide it by `5`.
5. After these steps:
    - If result = `1` → **ugly number**.
    - Else → **not ugly number**.

---

## 🔹 Example Dry Run

Input: `6`

- Divide by `2`: `6 / 2 = 3`.
- Divide by `3`: `3 / 3 = 1`.
- Result = `1` → ✅ Ugly number.

Input: `7`

- Not divisible by `2`, `3`, or `5`.
- Stays `7` → ❌ Not ugly.

---

# 🖥️ Solutions

---

## 🔹 C++ Solution

```cpp
#include <iostream>
using namespace std;

bool isUgly(int num) {
    if (num <= 0) return false; // Must be positive
    while (num % 2 == 0) num /= 2;
    while (num % 3 == 0) num /= 3;
    while (num % 5 == 0) num /= 5;
    return num == 1;
}

int main() {
    int n;
    cin >> n;
    if (isUgly(n))
        cout << "yes" << endl;
    else
        cout << "no" << endl;
    return 0;
}

```

---

## 🔹 Python Solution

```python
def is_ugly(num):
    if num <= 0:
        return False
    for factor in [2, 3, 5]:
        while num % factor == 0:
            num //= factor
    return num == 1

n = int(input())
print("yes" if is_ugly(n) else "no")

```

---

## 🔹 Java Solution

```java
import java.util.Scanner;

public class UglyNumber {
    public static boolean isUgly(int num) {
        if (num <= 0) return false;

        while (num % 2 == 0) num /= 2;
        while (num % 3 == 0) num /= 3;
        while (num % 5 == 0) num /= 5;

        return num == 1;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();

        if (isUgly(n))
            System.out.println("yes");
        else
            System.out.println("no");

        sc.close();
    }
}

```

---

✅ These versions are **universal** (no shortcuts).  
✅ Works for all inputs within integer range.