# 📘 Notes: Largest Product in a Series

### 🔹 Problem Statement

- You are given:
    1. An integer **K** (size of consecutive digits).
    2. A **string of digits** (series).
- Task: Find the **largest product** formed by multiplying **K consecutive digits**.

---

### 🔹 Key Concepts

1. **Substring Extraction** → Take groups of K digits.
2. **Digit Conversion** → Convert each character into an integer.
3. **Multiplication** → Compute product of digits.
4. **Comparison** → Keep track of maximum product found.

---

### 🔹 Step-by-Step Approach

1. Input K and the string series.
2. Initialize `maxProduct = 0`.
3. Loop from `i = 0` to `len(series) - K`.
    - Extract substring `series[i : i+K]`.
    - Multiply digits of this substring.
    - If product > maxProduct → update maxProduct.
4. Print `maxProduct`.

---

### 🔹 Example Walkthrough

Input:  
```
K = 3  
series = "2709360626"
```

Check all 3-digit groups:

- "270" → 2×7×0 = 0
- "709" → 7×0×9 = 0
- "093" → 0×9×3 = 0
- "936" → 9×3×6 = 162 ✅
- "360" → 3×6×0 = 0
- "606" → 6×0×6 = 0
- "062" → 0×6×2 = 0
- "626" → 6×2×6 = 72

Maximum = **162**

Output:  
```
162
```

---

# 🖥 Solutions

---

### ✅ Python

```python
k = int(input())
series = input().strip()

max_product = 0

for i in range(len(series) - k + 1):
    product = 1
    for j in range(k):
        product *= int(series[i + j])
    if product > max_product:
        max_product = product
        
print(max_product)

```

---

### ✅ C++

```cpp
#include <iostream>
#include <string>
using namespace std;

int main() {
    int k;
    string series;
    cin >> k >> series;
    long long maxProduct = 0;
    for (int i = 0; i <= series.size() - k; i++) {
        int product = 1;
        for (int j = 0; j < k; j++) {
            product *= (series[i + j] - '0');
        }
        if (product > maxProduct) {
            maxProduct = product;
        }
    }
    cout << maxProduct << endl;
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
        int k = sc.nextInt();
        String series = sc.next();
        long maxProduct = 0;
        for (int i = 0; i <= series.length() - k; i++) {
            int  product = 1;
            for (int j = 0; j < k; j++) {
                product *= (series.charAt(i + j) - '0');
            }
            if (product > maxProduct) {
                maxProduct = product;
            }
        }
        System.out.println(maxProduct);
    }
}

```