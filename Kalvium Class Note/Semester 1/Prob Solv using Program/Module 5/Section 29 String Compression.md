# 📒 5.29 String Compression

---

## 🔹 Problem Statement

**Task:** Compress a string by counting **consecutive occurrences** of each character.

- Represent each character followed by its count
- If the **compressed string** is **longer** than the original, keep the original

---

## 🔹 Example

**Input:**

```
aaabbbbccddd
```

**Output:**

```
a3b4c2d3
```

**Explanation:**

- a → 3 times → `a3`
- b → 4 times → `b4`
- c → 2 times → `c2`
- d → 3 times → `d3`

Compressed string = `a3b4c2d3` (shorter than original → output compressed)

---

## 🔹 Approach

1. **Initialize variables:**
    - `compressed = ""`
    - `count = 1`
2. **Iterate through the string:**
    - Compare each character with the next one
    - If same → increment count
    - If different → append `char + count` to `compressed` and reset count
3. **Edge Case:**
    - Add the last character and count after the loop
4. **Compare lengths:**
    - If `len(compressed) < len(original)` → print compressed
    - Else → print original

---

## 🔹 Python Implementation

```python
s = input()
compressed = ""
count = 1

for i in range(1, len(s)):
    if s[i] == s[i-1]:
        count += 1
    else:
        compressed += s[i-1] + str(count)
        count = 1

# Add the last character
compressed += s[-1] + str(count)

# Output the shorter string
print(compressed if len(compressed) < len(s) else s)

```

---

## 🔹 C++ Implementation

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    string s;
    cin >> s;
    string compressed = "";
    int count = 1;

    for(int i = 1; i < s.length(); i++){
        if(s[i] == s[i-1])
            count++;
        else{
            compressed += s[i-1] + to_string(count);
            count = 1;
        }
    }
    compressed += s.back() + to_string(count);

    cout << (compressed.length() < s.length() ? compressed : s) << endl;
    return 0;
}

```

---

## 🔹 Java Implementation

```java
import java.util.*;
public class StringCompression {
    public static void main(String[] args){
        Scanner sc = new Scanner(System.in);
        String s = sc.next();
        StringBuilder compressed = new StringBuilder();
        int count = 1;
        for(int i = 1; i < s.length(); i++){
            if(s.charAt(i) == s.charAt(i-1)){
                count++;
            } else {
                compressed.append(s.charAt(i-1)).append(count);
                count = 1;
            }
        }
        compressed.append(s.charAt(s.length()-1)).append(count);
        System.out.println(compressed.length() < s.length() ? compressed : s);
    }
}

```

---

## 🔹 Complexity Analysis

- **Time Complexity:** O(N) → iterate once through string
- **Space Complexity:** O(N) → for storing compressed string

---

## 🔹 Key Takeaways

- Efficiently handles **consecutive character counting**
- Useful for **basic string compression** in text processing
- Always compare compressed vs original **length** before output