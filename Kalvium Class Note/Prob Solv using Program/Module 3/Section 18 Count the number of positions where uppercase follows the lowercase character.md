## ✅ C++ Solution

```c++
#include <iostream>
using namespace std;

int main() {
    string str;
    cin >> str;
    int count = 0;
    for (int i = 0; i < str.size() - 1; i++) {
        if ((str[i] >= 'a' && str[i] <= 'z') && (str[i + 1] >= 'A' && str[i + 1] <= 'Z')) {
            count++;
        }
    }
    cout << count << endl;
    return 0;
}

```

---

## ✅ Python Solution

```python
s = input()

count = 0
for i in range(len(s) - 1):
    if s[i].islower() and s[i+1].isupper():
        count += 1

print(count)

```

---

## ✅ Java Solution

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String str = sc.nextLine();
        int count = 0;
        for (int i = 0; i < str.length() - 1; i++) {
            char ch1 = str.charAt(i);
            char ch2 = str.charAt(i + 1);
            if (Character.isLowerCase(ch1) && Character.isUpperCase(ch2)) {
                count++;
            }
        }
        System.out.println(count);
        sc.close();
    }
}

```

---

### 🔎 Example Run

**Input:**

```
heLLo
```

**Output:**

```
1
```

👉 Because `"eL"` is the only lowercase–uppercase pair.