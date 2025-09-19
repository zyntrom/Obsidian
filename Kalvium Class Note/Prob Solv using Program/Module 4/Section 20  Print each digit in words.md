# 📘 Notes: Print Each Digit in Words

### 🔹 Problem Statement

- Input: A number `n`.
- Output: Print each digit in **words**, in **reverse order** if number has more than one digit.

---

### 🔹 Key Concepts

1. **Digit Extraction** → Use modulus `% 10` and division `/ 10`.
2. **Mapping Digits to Words** → Store words in an array (Python list / C++ array / Java array).
    - Example: `arr = ["zero", "one", "two", "three", "four", "five", "six", "seven", "eight", "nine"]`
3. **Reverse Order** → Extract digits from right to left → automatically gives reversed output.
4. **Loop** → Keep dividing until the number becomes `0`.

---

### 🔹 Example Walkthrough

Input: `23`

- Step 1: Last digit = `3` → word = `"three"`
- Step 2: Next digit = `2` → word = `"two"`
- Output: `"three two"` ✅

---

# 🖥 Solutions

---

### ✅ Python

```python
arr = ["zero","one","two","three","four","five","six","seven","eight","nine"]

num = int(input())
while num > 0:
    digit = num % 10
    print(arr[digit], end=" ")
    num //= 10

```

---

### ✅ C++

```cpp
#include <iostream>
using namespace std;

int main() {
    string arr[] = {"zero","one","two","three","four","five","six","seven","eight","nine"};
    int num;
    cin >> num;

    while(num > 0) {
        int digit = num % 10;
        cout << arr[digit] << " ";
        num /= 10;
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
        String[] arr = {"zero","one","two","three","four","five","six","seven","eight","nine"};
        Scanner sc = new Scanner(System.in);
        int num = sc.nextInt();
        while(num > 0) {
            int digit = num % 10;
            System.out.print(arr[digit] + " ");
            num /= 10;
        }
    }
}

```

---

✅ **Explanation:**

- Each language stores digit-to-word mapping in an array.
- `% 10` extracts the last digit, `/ 10` removes it.
- Printing in this loop naturally gives the **reverse order**.