## 🔹 Problem Restatement

We need to check if a number is **pandigital**.  
A number is pandigital if it contains **all digits from 1 to N exactly once**, where **N** is the number of digits in the number.

---

## 🔹 Step-by-Step Approach

1. **Extract digits manually**
    - Use modulo (`% 10`) to get the last digit.
    - Use integer division (`// 10`) to remove the last digit.
    - Store the digits.
2. **Count total digits (N)**
    - While extracting digits, count how many digits there are.
3. **Check conditions for pandigital**
    - All digits must be **between 1 and N**.
    - No digit should repeat.
    - The number must contain **all digits from 1 to N**.

---

## 🔹 Universal Python Code

```python
def is_pandigital(num):
    digits = [0] * 10
    count = 0
    temp = num
    while temp > 0:
        d = temp % 10
        if d == 0:
            return False  # 0 not allowed
        if digits[d] > 0:
            return False  # duplicate digit
        digits[d] = 1
        temp //= 10
        count += 1
    for i in range(1, count + 1):
        if digits[i] == 0:
            return False
    return True

num = int(input())
print("Yes" if is_pandigital(num) else "No")

```

---

## C++ Program:

```cpp
#include <iostream>
using namespace std;

bool isPandigital(int num) {
    int digits[10] = {0};
    int count = 0, temp = num;
    
    while (temp > 0) {
        int d = temp % 10;
        if (d == 0) return false;     // 0 not allowed
        if (digits[d] > 0) return false; // duplicate digit
        digits[d] = 1;
        temp /= 10;
        count++;
    }
    
    // check if we have all digits from 1 to count
    for (int i = 1; i <= count; i++) {
        if (digits[i] == 0) return false;
    }
    return true;
}

int main() {
    int num;
    cin >> num;
    cout << (isPandigital(num) ? "Yes" : "No") << endl;
    return 0;
}
```

## Java Program:

```java
import java.util.Scanner;

public class PandigitalChecker {
    public static boolean isPandigital(int num) {
        int[] digits = new int[10];
        int count = 0;
        int temp = num;
        while (temp > 0) {
            int d = temp % 10;
            if (d == 0) return false; // 0 not allowed
            if (digits[d] > 0) return false; // duplicate digit
            digits[d] = 1;
            temp /= 10;
            count++;
        }
        for (int i = 1; i <= count; i++) {
            if (digits[i] == 0) return false;
        }
        return true;
    }
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int num = sc.nextInt();
        System.out.println(isPandigital(num) ? "Yes" : "No");
    }
}

```
## 🔹 Example Walkthrough

### Input:

```
54321
```
### Process:

- Extract digits → [1, 2, 3, 4, 5]
- Count = 5
- Check range → all digits are between 1 and 5 ✅
- Check duplicates → none ✅
- Check if all numbers from 1 to 5 exist → yes ✅

### Output:

```
Yes
```