# 📘 Notes: Print All Prime Numbers ≤ N

## Definition

- A **prime number** is a number **greater than 1** that has **no divisors** other than **1 and itself**.
- First few primes → 2, 3, 5, 7, 11, 13, 17...
- **Composite numbers** → numbers that have more than two divisors (e.g., 4, 6, 8, 9, 12).

---

## Steps to Solve

1. **Input Handling** → Read integer `N`.
2. **Loop through numbers** → For each number `i` from 2 to N:
    - Check if `i` is prime.
3. **Prime Check**:
    - A number `i` is prime if it is **not divisible** by any number from `2` to `sqrt(i)`.
    - If divisible → Not prime.
    - Else → Prime.
4. **Output** → Print all prime numbers separated by commas.

---

## Example Walkthrough

Input: `N = 5`
- Check numbers 2 to 5:
    - 2 → prime
    - 3 → prime
    - 4 → divisible by 2 → not prime
    - 5 → prime
- Output → `2,3,5,`

---

# 💻 Solutions

---
```embed
title: "L3. Check if a Number if Prime or not | Maths Playlist"
image: "https://i.ytimg.com/vi/MJcckSfoYdI/maxresdefault.jpg"
description: "Check out TUF+:https://takeuforward.org/plus?source=youtubeFind DSA, LLD, OOPs, Core Subjects, 1000+ Premium Questions company wise, Aptitude, SQL, AI doubt ..."
url: "https://youtu.be/MJcckSfoYdI"
favicon: ""
aspectRatio: "56.25"
```

### ✅ C++ Solution

```cpp
#include <iostream>
#include <cmath>
using namespace std;

bool isPrime(int num) {
    if (num < 2) return false;
    for (int i = 2; i <= sqrt(num); i++) {
        if (num % i == 0) return false;
    }
    return true;
}
int main() {
    int N;
    cin >> N;
    for (int i = 2; i <= N; i++) {
        if (isPrime(i)) {
            cout << i << ",";
        }
    }
    cout << endl;
    return 0;
}

```
---

### ✅ Python Solution

```python
import math

def is_prime(num):
    if num < 2:
        return False
    for i in range(2, int(math.sqrt(num)) + 1):
        if num % i == 0:
            return False
    return True

N = int(input("Enter N: "))

for i in range(2, N + 1):
    if is_prime(i):
        print(i, end=",")

```

---

### ✅ Java Solution

```java
import java.util.Scanner;

public class PrimeNumbers {
    static boolean isPrime(int num) {
        if (num < 2) return false;
        for (int i = 2; i <= Math.sqrt(num); i++) {
            if (num % i == 0) return false;
        }
        return true;
    }
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int N = sc.nextInt();
        sc.close();
        for (int i = 2; i <= N; i++) {
            if (isPrime(i)) {
                System.out.print(i + ",");
            }
        }
    }
}

```

---

# 📝 Explanation in Simple Words

- Start from **2** (smallest prime).
- For each number up to **N**, check if it can be divided evenly by any number other than 1 and itself.
- If not divisible → print it as prime.
- Stop at √N for efficiency (no need to check all numbers).