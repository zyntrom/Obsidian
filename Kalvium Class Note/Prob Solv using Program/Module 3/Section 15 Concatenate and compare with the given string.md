Here’s the clean cpp code:

```cpp
#include <iostream>
#include <string>
using namespace std;

int main() {
    string str1, str2, given;
    // Input: two strings in the first line
    cin >> str1 >> str2;
    // Input: the string to compare in the second line
    cin >> given;
    // Concatenate str1 and str2
    string combined = str1 + str2;
    // Compare concatenated string with the given one
    if (combined == given) {
        cout << "yes";
    } else {
        cout << "no";
    }
    return 0;
}

```

### ✅ Explanation step by step:

1. `cin >> str1 >> str2;` → takes the two strings.
2. `cin >> given;` → takes the third string.
3. `string combined = str1 + str2;` → concatenates using `+`.
4. `if (combined == given)` → checks if concatenated string matches the given one.
5. Prints `"yes"` if equal, `"no"` otherwise.

---

Here’s the **solution in cpp, Python, and Java** for your problem:

---

### 🔹 cpp Solution

```cpp
#include <iostream>
using namespace std;

int main() {
    string str1, str2, str;
    cin >> str1 >> str2;   // first line input (two strings)
    cin >> str;            // second line input (third string)
    string concat = str1 + str2;
    if (concat == str)
        cout << "yes";
    else
        cout << "no";
    return 0;
}

```

---

### 🔹 Python Solution

```python
str1, str2 = input().split()   # first line input (two strings)
str3 = input()                 # second line input (third string)

if str1 + str2 == str3:
    print("yes")
else:
    print("no")

```

---

### 🔹 Java Solution

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        
        String str1 = sc.next();
        String str2 = sc.next();
        String str3 = sc.next();
        
        String concat = str1 + str2;
        
        if (concat.equals(str3))
            System.out.println("yes");
        else
            System.out.println("no");
    }
}

```

---

⚡ All 3 programs follow the same **approach**:

1. Take two strings as first input line.
2. Take third string as second input line.
3. Concatenate first two strings.
4. Compare result with third string using == (Python, cpp) or `.equals()` (Java).
5. Print `"yes"` or `"no"`.