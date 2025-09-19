# 📘 Notes: Frequency of Each Digit

### 🔹 Problem Statement

- Input: A positive integer `n`.
- Task: Count and **print the frequency** of each digit in `n`.
- Output format: `digit:frequency` for digits that appear in `n`.
- Example:  
    Input: `231212`  
    Output:  
    1:2  
    2:3  
    3:1

---

### 🔹 Key Concepts

1. **Extract Digits** → Use modulus `% 10` to get the last digit.
2. **Count Frequency** → Use an array of size 10 (for digits 0–9).
3. **Remove Last Digit** → Use integer division `num //= 10`.
4. **Print Result** → Only print digits whose frequency is greater than 0.

---

### 🔹 Step-by-Step Approach

1. Read input `n`.
2. Initialize `freq[10] = {0}` (array for digits 0–9).
3. While `n > 0`:
    - `digit = n % 10` → extract last digit
    - `freq[digit] += 1` → increment count
    - `n = n // 10` → remove last digit
4. Loop through `freq` array and print `digit:frequency` for non-zero counts.

---

### 🔹 Example Walkthrough

Input: `231212`

- Extract digits: 2,1,2,1,3,2
- Frequency array: [0,2,3,1,0,0,0,0,0,0]
- Output:  
    1:2  
    2:3  
    3:1 ✅

---

# 🖥 Solutions

---

### ✅ Python

```python
num = int(input())
freq = [0]*10

while num > 0:
    digit = num % 10
    freq[digit] += 1
    num //= 10

for i in range(10):
    if freq[i] > 0:
        print(f"{i}:{freq[i]}")

```

---

### ✅ C++

```cpp
#include <iostream>
using namespace std;

int main() {
    int num;
    cin >> num;
    int freq[10] = {0};
    while (num > 0) {
        int digit = num % 10;
        freq[digit]++;
        num /= 10;
    }
    for (int i = 0; i < 10; i++) {
        if (freq[i] > 0) {
            cout << i << ":" << freq[i] << endl;
        }
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
        int num = sc.nextInt();
        int[] freq = new int[10];
        while (num > 0) {
            int digit = num % 10;
            freq[digit]++;
            num /= 10;
        }
        for (int i = 0; i < 10; i++) {
            if (freq[i] > 0) {
                System.out.println(i + ":" + freq[i]);
            }
        }
    }
}

```
---

✅ **Explanation:**

- The key is **digit extraction** using `% 10` and `// 10`.
    
- A simple array keeps count of each digit.
    
- Finally, only digits that appear at least once are printed.