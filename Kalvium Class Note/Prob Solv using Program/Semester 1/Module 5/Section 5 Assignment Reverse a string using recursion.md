# 🧠 Assignment: Reverse a String Using Recursion

---

## 🌍 1. Problem Statement

Write a program that **reverses a string** using **recursion**.

**Requirements:**

- Input: A string without spaces
- Output: The reversed string
- If input contains spaces → display error and terminate

**Examples:**

|Input|Output|
|---|---|
|hello|olleh|
|recursion|noisrucer|
|hello world|Error: No spaces allowed!|

---

## ⚙️ 2. Approach to Solve the Problem

1. **Input Validation:**
    - Check if the string contains spaces → print error and exit.
2. **Recursive Function Logic:**
    - Base Case: If string is empty → return empty string `""`
    - Recursive Step:
        - Take the **last character** of the string
        - Append it to the **reversal of the rest of the string**
3. **Return Result:**
    - The recursion unwinds and builds the reversed string step by step.

---

## 🌳 3. Recursion Tree Example (`"hello"`)

```cpp
         reverse("hello")
        /            \
     "o" +      reverse("hell")
                 /            \
             "l" +      reverse("hel")
                         /            \
                     "l" +      reverse("he")
                                 /         \
                             "e" +    reverse("h")
                                       /
                                     "h" (Base Case)

```

**Stepwise Return:**

- reverse("h") → "h"
- reverse("he") → "e" + "h" = "eh"
- reverse("hel") → "l" + "eh" = "leh"
- reverse("hell") → "l" + "leh" = "lleh"
- reverse("hello") → "o" + "lleh" = "olleh"

---

## 🧮 4. Dry Run of Recursion

|Function Call|String Input|Returns|
|---|---|---|
|reverse("hello")|"hello"|"o" + reverse("hell")|
|reverse("hell")|"hell"|"l" + reverse("hel")|
|reverse("hel")|"hel"|"l" + reverse("he")|
|reverse("he")|"he"|"e" + reverse("h")|
|reverse("h")|"h"|"h" (Base Case)|

**Final Output:** `"olleh"`

---

## 💻 5. Universal Code (Easy to Understand)

### Java

`public class ReverseString {     static String reverse(String str) {         if (str.isEmpty()) // Base case             return "";         // Last character + reverse of remaining string         return str.charAt(str.length() - 1) + reverse(str.substring(0, str.length() - 1));     }      public static void main(String[] args) {         String input = "hello";          // Check for spaces         if (input.contains(" ")) {             System.out.println("Error: No spaces allowed!");             return;         }          System.out.println(reverse(input));     } }`

---

### C++

`#include <iostream> #include <string> using namespace std;  string reverse(string str) {     if (str.empty()) // Base case         return "";     return str[str.length() - 1] + reverse(str.substr(0, str.length() - 1)); }  int main() {     string input = "hello";      // Check for spaces     if (input.find(' ') != string::npos) {         cout << "Error: No spaces allowed!" << endl;         return 0;     }      cout << reverse(input) << endl; }`

---

### Python

`def reverse(s):     if s == "":  # Base case         return ""     return s[-1] + reverse(s[:-1])  # Last char + reverse of remaining  input_str = "hello"  # Check for spaces if " " in input_str:     print("Error: No spaces allowed!") else:     print(reverse(input_str))`

---

## ⚡ 6. Explanation of the Code

1. **Base Case:**
    
    - `if str is empty → return ""`
        
    - Stops recursion when all characters have been processed
        
2. **Recursive Step:**
    
    - `last character + reverse(remaining string)`
        
    - Builds reversed string as recursion unwinds
        
3. **Input Validation:**
    
    - Checks for spaces and prints error if found
        
4. **Iterative vs Recursive:**
    
    - Recursive approach is **cleaner and easier to understand** for string reversal
        
    - Iterative approach would require a loop and a temporary string
        

---

## 🗺️ 7. Mind Map Summary

`Reverse String Recursion ├── Input Validation │   └── No spaces allowed ├── Base Case │   └── Empty string → return "" ├── Recursive Step │   └── Last character + reverse(remaining string) ├── Recursion Tree Example │   └── reverse("hello") ├── Dry Run │   └── Stepwise building of reversed string └── Output     └── Reversed string`

---

## 📚 8. Key Points for Exam

- Recursion **calls itself on smaller input**
    
- Always define **base case** to stop recursion
    
- For strings: use **last character + reverse of remaining string**
    
- Validate input to handle **edge cases** (spaces, empty string, single char)