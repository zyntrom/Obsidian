### ✅ cpp Solution

```cpp
#include <iostream>
using namespace std;

int main() {
    string str;
    cin >> str;
    string result = "";
    for (int i = 0; i < str.size(); i++) {
        if ((str[i] >= 'a' && str[i] <= 'z') || (str[i] >= 'A' && str[i] <= 'Z')) {
            result += str[i];
        }
    }
    cout << result << endl;
    return 0;
}

```

---

### ✅ Python Solution

```python
s = input()

result = ""
for ch in s:
    if ch.isalpha():   # check if character is alphabet
        result += ch

print(result)

```

---

### ✅ Java Solution

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String str = sc.nextLine();
        String result = "";
        for (int i = 0; i < str.length(); i++) {
            char ch = str.charAt(i);
            if ((ch >= 'a' && ch <= 'z') || (ch >= 'A' && ch <= 'Z')) {
                result += ch;
            }
        }
        System.out.println(result);
        sc.close();
    }
}

```

---

👉 All three programs:

- Take the input string.
- Loop through each character.
- Keep only alphabets (A–Z, a–z).
- Print the result.