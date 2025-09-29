Here are solutions in **cpp** and **Python** (since your course is using those two):

---

## ✅ cpp Solution

```cpp
#include <iostream>
using namespace std;

string removeBAndAC(string s) {
    string result = "";
    int i = 0;
    while (i < s.length()) {
        if (s[i] == 'b') {
            // Skip 'b'
            i++;
        }
        else if (i + 1 < s.length() && s[i] == 'a' && s[i + 1] == 'c') {
            // Skip "ac"
            i += 2;
        }
        else {
            // Keep character
            result += s[i];
            i++;
        }
    }
    return result;
}

int main() {
    string str;
    cin >> str;
    cout << removeBAndAC(str) << endl;
    return 0;
}

```

---

## ✅ Python Solution

```python
def remove_b_and_ac(s: str) -> str:
    result = ""
    i = 0
    while i < len(s):
        if s[i] == 'b':
            i += 1  # skip 'b'
        elif i + 1 < len(s) and s[i] == 'a' and s[i+1] == 'c':
            i += 2  # skip "ac"
        else:
            result += s[i]
            i += 1
    return result


# Input
s = input()
print(remove_b_and_ac(s))

```

---

### 🔎 Example Runs

**Input:**

```
aacbacc
```

**Output:**

```
ac
```

---

**Input:**

```
aacb
```

**Output:**

```
a
```