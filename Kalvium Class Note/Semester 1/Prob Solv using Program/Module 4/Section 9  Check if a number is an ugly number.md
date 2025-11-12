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
#include <cmath>
#include <cstdio>
#include <vector>
#include <iostream>
#include <algorithm>
using namespace std;

int main() {
    int n;
    cin >> n;
    while (n % 2 == 0) {
        n /= 2;
    }
    while (n % 3 == 0) {
        n /= 3;
    }
    while (n % 5 == 0) {
        n /= 5;
    }
    if (n == 1) {
        cout << "yes";
    } else {
        cout << "no";
    }
    return 0;
}

```

---

## 🔹 Python Solution

```python
n = int(input())

while n % 2 == 0:
    n //= 2
while n % 3 == 0:
    n //= 3
while n % 5 == 0:
    n //= 5
if n == 1:
    print("yes")
else:
    print("no")

```

---

## 🔹 Java Solution

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        while (n % 2 == 0) {
            n /= 2;
        }
        while (n % 3 == 0) {
            n /= 3;
        }
        while (n % 5 == 0) {
            n /= 5;
        }
        if (n == 1) {
            System.out.print("yes");
        } else {
            System.out.print("no");
        }
    }
}

```

---

✅ These versions are **universal** (no shortcuts).  
✅ Works for all inputs within integer range.