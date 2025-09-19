## 📒 Notes on the Problem

### 1. What is being asked?

- We’re given two numbers `a` and `b`, which represent a fraction `a/b` with `a < b`.
- We need to print **all possible reduced forms** of that fraction.
- If the fraction is already in lowest terms (i.e., it cannot be simplified), we print `-1`.

---

### 2. Key Mathematical Principles

- **Fraction reduction**: A fraction is reduced by dividing both numerator and denominator by their **greatest common divisor (GCD)**.
- Example:
    - `6/12` → GCD = 6 → `1/2`.
- But the problem wants **all possible reduced forms**.
    - That means: divide numerator and denominator by every divisor of GCD.

---

### 3. Steps to Solve

1. Find the GCD of `a` and `b`.
2. If GCD = 1 → fraction is already reduced → print `-1`.
3. Otherwise:
    - For each divisor `d` of GCD:
        - Print `(a/d)/(b/d)`.
    - Order them so the fraction gets smaller step by step.

---

### 4. Example Walkthrough

Input: `6 12`

- GCD(6,12) = 6
- Divisors of 6 → {1, 2, 3, 6}
- Reduced fractions:
    - `6/12` (d=1)
    - `3/6` (d=2)
    - `2/4` (d=3)
    - `1/2` (d=6)  
        Output: `3/6 2/4 1/2` (skip the original one, `6/12`).

---

## ✅ Final Explanation in Simple Words

We just keep dividing the numerator and denominator by **common factors** until we reach the simplest fraction. All intermediate reduced forms are included, but if the fraction is already simplest, we return `-1`.

---

## 💻 Solutions

### C++ Solution

```cpp
#include <iostream>
using namespace std;

int main() {
    int a, b;
    cin >> a >> b;
    bool found = false;

    for (int i = 2; i < b; i++) {
        if (a % i == 0 && b % i == 0) {
            cout << a / i << "/" << b / i << " ";
            found = true;
        }
    }
    if (!found) {
        cout << -1;
    }
    return 0;
}
```

---

### Python Solution

```python
a, b = map(int, input().split())
found = False

for i in range(2, b):
    if a % i == 0 and b % i == 0:
        print(f"{a//i}/{b//i}", end=" ")
        found = True

if not found:
    print(-1)

```

---

### Java Solution

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int a = sc.nextInt();
        int b = sc.nextInt();
        boolean found = false;
        for (int i = 2; i < b; i++) {
            if (a % i == 0 && b % i == 0) {
                System.out.print((a / i) + "/" + (b / i) + " ");
                found = true;
            }
        }
        if (!found) {
            System.out.print(-1);
        }
    }
}

```