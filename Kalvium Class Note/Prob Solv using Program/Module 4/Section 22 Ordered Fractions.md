### 1. Problem

- Given two integers `a` and `b` representing a fraction `a/b` (where `a < b`).
- Find all reduced forms of the fraction by dividing both numerator and denominator by the same integer.
- If the fraction is already in lowest terms, print `-1`.

---

### 2. Approach in Your Code

1. **Input**: Read `a` and `b`.
2. **Loop**: For every integer `i` from `2` to `b-1`:
    - Check if `i` divides both `a` and `b` (`a % i == 0 && b % i == 0`).
    - If true, print the fraction `(a/i)/(b/i)`.
    - Mark that we found at least one reduced form.
3. **Check**: If no divisor reduced the fraction → print `-1`.

---

### 3. Key Observations

- This approach checks **all possible divisors** of both `a` and `b`.
- It avoids directly calculating GCD — instead, it brute-forces divisibility.
- The loop goes up to `b-1`, but it’s safe (since denominator is always bigger).
- A `found` flag is used to track if any reduction was printed.

---

### 4. Example Walkthrough

Input: `6 12`

- Loop from `2` to `11`.
- When `i=2`: both divisible → print `3/6`.
- When `i=3`: both divisible → print `2/4`.
- When `i=6`: both divisible → print `1/2`.
- Output: `3/6 2/4 1/2`.

Input: `4 7`

- No `i` divides both.
- Output: `-1`.

---

### 5. Pros and Cons

✅ Easy to understand.  
✅ Doesn’t need GCD function.  
❌ Less efficient (loops through many values even if unnecessary).  
❌ For large `b`, it can be slow.

---

### 6. General Pattern

- **Brute force divisor checking**: Test all possible divisors.
- Use a **flag** to detect if no answer was found.
- Print results inline as you find them.

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