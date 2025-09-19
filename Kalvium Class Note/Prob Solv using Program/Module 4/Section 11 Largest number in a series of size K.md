# 📘 Notes: Largest Number in a Series of Size K

### 🔹 Problem Statement

- You are given:
    1. A **string of digits** (e.g., `"123332232"`)
    2. An integer **K** (size of the subarray).
- Task: Find the **largest number possible** that can be formed using **K consecutive digits** in the series.

---

### 🔹 Key Concepts

1. **String Manipulation** → Treat the series as a string so digits can be accessed individually.
2. **Substring Extraction** → Take substrings of length K from the string.
3. **Integer Conversion** → Convert substring into a number for comparison.
4. **Looping** → Iterate over all possible substrings of length K.

---

### 🔹 Step-by-Step Approach

1. Input the string `s` and integer `k`.
2. Initialize `maximum = 0`.
3. Loop over indices `i = 0` to `len(s) - k`.
    - Extract substring `s[i : i+k]`.
    - Convert it into an integer.
    - Compare with `maximum` → update if larger.
4. Print the final `maximum`.

---

### 🔹 Example Walkthrough

Input:  

```
s = "123332232", k = 2
```

Substrings of size 2:

- "12" → 12
- "23" → 23
- "33" → 33 ✅
- "32" → 32
- "22" → 22
- "23" → 23

Maximum = **33**

Output:  
```
33
```

---

# 🖥 Solutions

---

### ✅ Python

```python
s, k = input().split()
k = int(k)

maximum = 0
for i in range(len(s) - k + 1):
    num = int(s[i:i+k])
    if num > maximum:
        maximum = num

print(maximum)

```

---

### ✅ C++

```cpp
#include <iostream>
#include <string>
using namespace std;

int main() {
    string s;
    int k;
    cin >> s >> k;
    int maximum = 0;
    for (int i = 0; i <= s.size() - k; i++) {
        string sub = s.substr(i, k);
        int num = stoi(sub);
        if (num > maximum) {
            maximum = num;
        }
    }
    cout << maximum << endl;
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
        String s = sc.next();
        int k = sc.nextInt();
        int maximum = 0;
        for (int i = 0; i <= s.length() - k; i++) {
            String sub = s.substring(i, i + k);
            int num = Integer.parseInt(sub);
            if (num > maximum) {
                maximum = num;
            }
        }
        System.out.println(maximum);
    }
}

```

---