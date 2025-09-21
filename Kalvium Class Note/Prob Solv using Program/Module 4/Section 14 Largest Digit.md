# 📘 Notes: Largest Number with Given Sum and Digits

### 🔹 Problem Statement

- You are given two integers:
    - `s` → sum of digits
    - `d` → number of digits
- Task: Form the **largest possible number** with exactly `d` digits such that the sum of its digits is `s`.
- If not possible → print `-1`.

---

### 🔹 Key Concepts

1. **Greedy Approach** → Always put the largest possible digit in the **most significant place (leftmost)** to maximize the number.
2. **Digit Placement** → At each position, put `min(9, remaining sum)` and reduce the sum.
3. **Validity Check** → If `s > 9*d` (sum too large to fit in `d` digits) → Not possible.

---

### 🔹 Step-by-Step Approach

1. Read input `s, d`.
2. If `s > 9*d` → print `-1`.
3. Otherwise:
    - Start with an empty number string.
    - For each digit position from 1 to d:
        - Place `min(9, s)` in the current position.
        - Subtract this value from `s`.
4. Print the constructed number.

---

### 🔹 Example Walkthrough

Input: `s = 9, d = 2`

- Max sum possible with 2 digits = `18`. Since `9 <= 18`, valid.
- First digit → `min(9, 9) = 9`. Remaining sum = `0`.
- Second digit → `min(9, 0) = 0`. Remaining sum = `0`.

Final number = `90`. ✅

---

# 🖥 Solutions

```embed
title: "GFG POTD: 13/09/2023 | Largest Number Possible | Problem of the Day GeeksforGeeks"
image: "https://i.ytimg.com/vi/TY05-Nh2nuw/maxresdefault.jpg"
description: "Welcome to the daily solving of our PROBLEM OF THE DAY with Karan Mashru. We will discuss the entire problem step-by-step and work towards developing an opti..."
url: "https://youtu.be/TY05-Nh2nuw"
favicon: ""
aspectRatio: "56.25"
```

---

### ✅ Python

```python
s, d = map(int, input().split())

if (s > 9 * d or s <= 0 or d <= 0):
    print(-1)
else:
    result = ""
    for i in range(d):
        digit = min(9, s)
        result += str(digit)
        s -= digit
    print(result)

```

---

### ✅ C++

```cpp
#include <iostream>
using namespace std;

int main() {
    int s, d;
    cin >> s >> d;
    if (s > 9 * d || s <= 0 || d <= 0) {
        cout << -1 << endl;
    } else {
        string result = "";
        for (int i = 0; i < d; i++) {
            int digit = min(9, s);
            result += to_string(digit);
            s -= digit;
        }
        cout << result << endl;
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
        int s = sc.nextInt();
        int d = sc.nextInt();
        if (s > 9 * d || s <= 0 || d <= 0) {
            System.out.println(-1);
        } else {
            StringBuilder result = new StringBuilder();
            for (int i = 0; i < d; i++) {
                int digit = Math.min(9, s);
                result.append(digit);
                s -= digit;
            }
            System.out.println(result.toString());
        }
    }
}

```
---

✅ This uses a **greedy method** to always put the largest digit possible at the left, ensuring the final number is the largest.