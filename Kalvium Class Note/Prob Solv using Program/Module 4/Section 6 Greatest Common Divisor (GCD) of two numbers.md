# 📘 Notes: Greatest Common Divisor (GCD)

## Definition

- The **GCD (Greatest Common Divisor)** of two numbers is the **largest number that divides both numbers without leaving a remainder**.
- Also called **HCF (Highest Common Factor)**.

Example:

- GCD(24, 36) = 12
    - 24 = 12 × 2
    - 36 = 12 × 3

---

## Two Approaches

### 1) Brute Force Approach

- Start from 1 up to `min(n1, n2)`.
- Check which numbers divide both.
- Keep track of the largest divisor.
- **Time complexity → O(min(n1, n2))** (slow for large numbers).

---

### 2) Euclidean Algorithm (Efficient)

- Formula: **GCD(a, b) = GCD(b, a % b)**.
- Repeat until `b = 0`.
- The remaining `a` is the GCD.
- **Time complexity → O(log(min(n1, n2)))** (fast).

---

## Example Walkthrough

Input: `24 36`

- Brute Force:  
    Divisors of 24 = {1,2,3,4,6,8,12,24}  
    Divisors of 36 = {1,2,3,4,6,9,12,18,36}  
    Common divisors = {1,2,3,4,6,12} → largest = 12
    
- Euclidean:  
    GCD(36, 24)  
    → GCD(24, 36 % 24) = GCD(24, 12)  
    → GCD(12, 24 % 12) = GCD(12, 0)  
    → Answer = 12 ✅
    

---

# 💻 Solutions

---
```embed
title: "L68 - C Program to find the GCD of two numbers - Coding - TCS NQT | Ninja | Digital"
image: "https://i.ytimg.com/vi/KES9Z3rZZ6I/maxresdefault.jpg"
description: "This video is a simple and clear explanation of how to find GCD of two numbers.Solve Practice Questions & Topic Tests :https://packetprep.com/course/targettc..."
url: "https://youtu.be/KES9Z3rZZ6I"
favicon: ""
aspectRatio: "56.25"
```

```embed
title: "Basic Maths for DSA | Euclidean Algorithm | Strivers A2Z DSA Course"
image: "https://i.ytimg.com/vi/1xNbjMdbjug/maxresdefault.jpg"
description: "Check out TUF+:https://takeuforward.org/plus?source=youtubeFind DSA, LLD, OOPs, Core Subjects, 1000+ Premium Questions company wise, Aptitude, SQL, AI doubt ..."
url: "https://youtu.be/1xNbjMdbjug"
favicon: ""
aspectRatio: "56.25"
```

### ✅ C++ Solution (Euclidean)

```cpp
#include <iostream>
using namespace std;

int gcd(int a, int b) {
    while (b != 0) {
        int temp = b;
        b = a % b;
        a = temp;
    }
    return a;
}

int main() {
    int n1, n2;
    cin >> n1 >> n2;
    cout << gcd(n1, n2) << endl;
    return 0;
}

```

---

### ✅ Python Solution (Euclidean)

```python
# Function to calculate GCD
def gcd(a, b):
    while b != 0:
        temp = b
        b = a % b
        a = temp
    return a
n1, n2 = map(int, input().split())

print(gcd(n1, n2))
```

---

### ✅ Java Solution (Euclidean)

```java
import java.util.Scanner;

public class GCD {
    static int gcd(int a, int b) {
        while (b != 0) {
            int temp = b;
            b = a % b;
            a = temp;
        }
        return a;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n1 = sc.nextInt();
        int n2 = sc.nextInt();
        System.out.println(gcd(n1, n2));
    }
}

```

---

# 📝 Explanation in Simple Words

- The brute force method **checks all numbers** up to the smaller input → slow.
- The Euclidean method keeps **replacing the bigger number with the remainder** → fast.
- Eventually, one number becomes zero, and the other is the GCD.