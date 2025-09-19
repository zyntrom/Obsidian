# 📘 Notes: Working with Special Numbers (Pentagonal Numbers)

## Definition

- A **pentagonal number** is defined by the formula:  
    **Pn = n(3n − 1) / 2** where `n` is a positive integer.
- First few pentagonal numbers:  
    1, 5, 12, 22, 35, 51, 70, …

---

## Key Idea for This Problem

We are asked to **count pairs (Pn, Pn−K)** where:

- Either **Pn − Pn−K** is pentagonal, OR
- **Pn + Pn−K** is pentagonal.

---

## Step-by-Step Approach

1. **Input Handling** → Read `N` (upper limit for n) and `K`.
2. **Generate pentagonal numbers** up to `N`.
    - Use formula Pn = n(3n−1)/2 for n < N.
3. **Check pairs** (Pn, Pn−K):
    - If n−K ≥ 1 (valid index), compute:
        - `diff = Pn − Pn−K`
        - `sum = Pn + Pn−K`
    - Check if either `diff` or `sum` is pentagonal.
4. **Count valid pairs** and print the result.

---

## Checking if a Number is Pentagonal

A number `x` is pentagonal if:
**n = (1 + √(1 + 24x)) / 6** is a positive integer.

---

## Example Walkthrough

Input:

```
N = 10
K = 2
```

Pentagonal numbers (n=1..9):  
1, 5, 12, 22, 35, 51, 70, 92, 117

Check pair: P7 (70), P5 (35) → difference = 35 (pentagonal ✅).  
Count = 1.

Output → `1`.

---

# 💻 Solutions

---

### ✅ C++ Solution

```cpp
#include <iostream>
#include <cmath>
#include <vector>
using namespace std;

bool isPentagonal(int num) {
    if (num <= 0) return false;
    double n = (1 + sqrt(1 + 24 * num)) / 6;
    return n == (int)n;
}

int main() {
    int N, K;
    cin >> N >> K;
    vector<int> pentagonal(N);
    for (int i = 1; i < N; i++) {
        pentagonal[i] = i * (3 * i - 1) / 2;
    }
    int count = 0;
    for (int n = K + 1; n < N; n++) {
        int Pn = pentagonal[n];
        int Pnk = pentagonal[n - K]
        int diff = Pn - Pnk;
        int sum = Pn + Pnk;
        if (isPentagonal(diff) || isPentagonal(sum)) {
            count++;
        }
    }
    cout << count << endl;
    return 0;
}

```
---

### ✅ Python Solution

```python
import math

def is_pentagonal(num):
    if num <= 0:
        return False
    n = (1 + math.sqrt(1 + 24 * num)) / 6
    return n == int(n)

N = int(input())
K = int(input())

pentagonal = [0] * N
for i in range(1, N):
    pentagonal[i] = i * (3 * i - 1) // 2
count = 0
for n in range(K + 1, N):
    Pn = pentagonal[n]
    Pnk = pentagonal[n - K]
    diff = Pn - Pnk
    sum_val = Pn + Pnk
    if is_pentagonal(diff) or is_pentagonal(sum_val):
        count += 1

print(count)

```

---

### ✅ Java Solution

```java
import java.util.Scanner;

public class PentagonalNumbers {
    static boolean isPentagonal(int num) {
        if (num <= 0) return false;
        double n = (1 + Math.sqrt(1 + 24 * num)) / 6;
        return n == (int)n;
    }
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int N = sc.nextInt();
        int K = sc.nextInt();
        sc.close();
        int[] pentagonal = new int[N];
        for (int i = 1; i < N; i++) {
            pentagonal[i] = i * (3 * i - 1) / 2;
        }
        int count = 0;
        for (int n = K + 1; n < N; n++) {
            int Pn = pentagonal[n];
            int Pnk = pentagonal[n - K];
            int diff = Pn - Pnk;
            int sum = Pn + Pnk;
            if (isPentagonal(diff) || isPentagonal(sum)) {
                count++;
            }
        }
        System.out.println(count);
    }
}

```

---

# 📝 Explanation in Simple Words

- Generate pentagonal numbers up to N.
- For each valid pair `(Pn, Pn−K)` check two conditions:
    - Is `Pn − Pn−K` pentagonal?
    - Is `Pn + Pn−K` pentagonal?
- If yes, count it.
- Print the total count.