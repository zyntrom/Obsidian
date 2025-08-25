### 🔹 Problem Recap

You need to take:

1. A string `Str`.
2. A starting index `start` (0-based).
3. A length `n`.

Then print the substring starting at `start` with length `n`.

---

### ✅ C++ Solution

```c++
#include <iostream>
using namespace std;

int main() {
    string str;
    int start, n;
    
    cin >> str;          // input string
    cin >> start >> n;   // starting position and length
    
    string result = "";
    
    // extracting substring manually using loop
    for (int i = start; i < start + n && i < str.length(); i++) {
        result += str[i];
    }
    
    cout << result;
    return 0;
}

```

---

### ✅ Python Solution

`# input string s = input().strip() # input start and length start, n = map(int, input().split())  # extract substring using slicing substring = s[start:start+n]  print(substring)`

---

### ✅ Java Solution

`import java.util.Scanner;  public class Main {     public static void main(String[] args) {         Scanner sc = new Scanner(System.in);                  String str = sc.next();         // input string         int start = sc.nextInt();       // starting position         int n = sc.nextInt();           // length                  // make sure substring doesn't go out of range         int end = Math.min(start + n, str.length());                  String result = "";         for (int i = start; i < end; i++) {             result += str.charAt(i);         }                  System.out.println(result);     } }`

---

### 🔹 Example Run

**Input**

`abcdefgh 2 4`

**Output**

`cdef`