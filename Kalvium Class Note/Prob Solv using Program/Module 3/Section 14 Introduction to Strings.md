# 📝 Notes: Concatenate and Compare with the Given String

### Problem

- You are given **two strings**, say `s1` and `s2`.
- You are also given a **target string** `target`.
- Task:
    1. Concatenate `s1` and `s2`.
    2. Compare the result with `target`.
    3. Print `"Equal"` if both are same, otherwise `"Not Equal"`.

---

### 🔹 Step-by-step approach

1. Take input: `s1`, `s2`, `target`.
2. Concatenate `s1 + s2`.
3. Compare the result with `target`.
4. Output result.

---

## ✅ C++ Solution (using `string` class)

```c++
#include <iostream>
#include <string>
using namespace std;

int main() {
    string s1, s2, target;
    cin >> s1 >> s2 >> target;
    string combined = s1 + s2;
    if (combined == target) {
        cout << "Equal" << endl;
    } else {
        cout << "Not Equal" << endl;
    }
    return 0;
}

```

---

## ✅ Python Solution (universal, no shortcuts)

```python
# Read input
s1 = input().strip()
s2 = input().strip()
target = input().strip()

# Concatenate
combined = s1 + s2

# Compare
if combined == target:
    print("Equal")
else:
    print("Not Equal")

```

---

## ✅ Java Solution

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String s1 = sc.nextLine();
        String s2 = sc.nextLine();
        String target = sc.nextLine();
        String combined = s1 + s2;
        if (combined.equals(target)) {
            System.out.println("Equal");
        } else {
            System.out.println("Not Equal");
        }
        sc.close();
    }
}

```

---