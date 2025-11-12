# 📘 Notes: Print the Sum of Digits

### 🔹 Problem Statement

- You are given a number.
- Task: Find the **sum of its digits**.

---

### 🔹 Key Concepts

1. **Modulus Operator (%)** → To extract the last digit.
2. **Integer Division (// or /)** → To remove the last digit.
3. **Loop** → Repeat until the number becomes 0.
4. **Sum Accumulation** → Keep adding digits to `sum`.

---

### 🔹 Step-by-Step Approach

1. Take input number `n`.
2. Initialize `sum = 0`.
3. While `n > 0`:
    - Extract digit → `digit = n % 10`.
    - Add digit to sum.
    - Remove last digit → `n = n // 10`.
4. Print `sum`.

---

### 🔹 Example Walkthrough

```
Input: 2334
```
Steps:

- 2334 % 10 = 4 → sum = 4
- 2334 // 10 = 233
- 233 % 10 = 3 → sum = 4+3=7
- 233 // 10 = 23
- 23 % 10 = 3 → sum = 7+3=10
- 23 // 10 = 2
- 2 % 10 = 2 → sum = 10+2=12
- 2 // 10 = 0 → stop

```
Output: 12
```

---

# 🖥 Solutions

---

```embed
title: "Basic Maths for DSA | Euclidean Algorithm | Strivers A2Z DSA Course"
image: "https://i.ytimg.com/vi/1xNbjMdbjug/maxresdefault.jpg"
description: "Check out TUF+:https://takeuforward.org/plus?source=youtubeFind DSA, LLD, OOPs, Core Subjects, 1000+ Premium Questions company wise, Aptitude, SQL, AI doubt ..."
url: "https://youtu.be/1xNbjMdbjug"
favicon: ""
aspectRatio: "56.25"
```

### ✅ Python

```python
n = int(input())
total = 0

while n > 0:
    digit = n % 10
    total += digit
    n //= 10

print(total)

```

---

### ✅ C++

```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cin >> n;
    int sum = 0;
    while (n > 0) {
        int digit = n % 10;
        sum += digit;
        n = n / 10;
    }
    cout << sum << endl;
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
        int n = sc.nextInt();
        int sum = 0;
        while (n > 0) {
            int digit = n % 10;
            sum += digit;
            n = n / 10;
        }
        System.out.println(sum);
    }
}

```

---