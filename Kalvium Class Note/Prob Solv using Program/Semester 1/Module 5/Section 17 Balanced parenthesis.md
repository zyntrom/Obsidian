# 📒 Notes: Balanced Parentheses

---

## 🔹 Problem Statement

Given a string `s` containing only the characters:

```
'(', ')', '{', '}', '[', ']'
```

Determine if the string is **valid**.

A string is valid if:

1. Open brackets are closed by the **same type** of bracket.
2. Brackets are closed in the **correct order**.
3. Every closing bracket has a corresponding opening bracket.

---

### Example 1:

**Input:**

```
s = "()"
```

**Output:**

```
true
```

### Example 2:

**Input:**

```
s = "()[]{}"
```

**Output:**

```
true
```

### Example 3:

**Input:**

```
s = "(]"
```

**Output:**

```
false
```

---

## 🔹 Approach (Stack-based)

1. **Initialize a stack** to keep track of opening brackets.
2. **Traverse the string** character by character:
    - If it is an **opening bracket** `(`, `{`, `[` → push it to the stack.
    - If it is a **closing bracket** `)`, `}`, `]` → check the stack:
        - If the stack is empty → **invalid string** → return `false`
        - Else, pop the top of the stack and check:
            - If it matches the corresponding opening bracket → continue
            - Else → **invalid string** → return `false`
3. After traversal:
    - If the stack is empty → all brackets matched → **return true**
    - Else → unmatched brackets remain → **return false**

---

### 🔹 Key Points

- Use **stack** to maintain order of opening brackets.
- Check **matching pairs** carefully:
    - `(` → `)`
    - `{` → `}`
    - `[` → `]`
- **Empty stack on closing bracket** → immediately invalid.

---

# 🔹 Code Implementations

---

### ✅ Python Implementation

```python
def isValid(s):
    stack = []
    for c in s:
        # Step 1: Push opening brackets
        if c in "({[":
            stack.append(c)
        else:
            # Step 2: Check for empty or mismatched
            if not stack:
                return False
            top = stack.pop()
            if (c == ')' and top != '(') or \
               (c == '}' and top != '{') or \
               (c == ']' and top != '['):
                return False
    # Step 3: Stack should be empty if valid
    return len(stack) == 0


# Test cases
print(isValid("()"))        # True
print(isValid("()[]{}"))    # True
print(isValid("(]"))        # False
print(isValid("([{}])"))    # True
print(isValid("((("))       # False

```

---

### ✅ Java Implementation

```java
import java.util.Stack;

public class BalancedParenthesis {
    public static boolean isValid(String s) {
        Stack<Character> stack = new Stack<>();
        for (char c : s.toCharArray()) {
            // Step 1: Push opening brackets
            if (c == '(' || c == '{' || c == '[') {
                stack.push(c);
            } 
            // Step 2: Handle closing brackets
            else {
                // If stack is empty, no matching opening
                if (stack.isEmpty()) return false;
                char top = stack.pop();
                // Check if top matches closing bracket
                if ((c == ')' && top != '(') ||
                    (c == '}' && top != '{') ||
                    (c == ']' && top != '[')) {
                    return false;
                }
            }
        }
        // Step 3: If stack empty → all matched
        return stack.isEmpty();
    }
    public static void main(String[] args) {
        System.out.println(isValid("()"));       // true
        System.out.println(isValid("()[]{}"));   // true
        System.out.println(isValid("(]"));       // false
        System.out.println(isValid("([{}])"));   // true
        System.out.println(isValid("((("));      // false
    }
}

```
---

### ✅ C++ Implementation

```cpp
#include <iostream>
#include <stack>
#include <string>
using namespace std;

bool isValid(string s) {
    stack<char> st;
    for (char c : s) {
        // Step 1: Push opening brackets
        if (c == '(' || c == '{' || c == '[') {
            st.push(c);
        } 
        // Step 2: Handle closing brackets
        else {
            if (st.empty()) return false;
            char top = st.top();
            st.pop();
            if ((c == ')' && top != '(') ||
                (c == '}' && top != '{') ||
                (c == ']' && top != '[')) {
                return false;
            }
        }
    }
    // Step 3: Return true if all matched
    return st.empty();
}

int main() {
    cout << boolalpha; // print true/false instead of 1/0
    cout << isValid("()") << endl;       // true
    cout << isValid("()[]{}") << endl;   // true
    cout << isValid("(]") << endl;       // false
    cout << isValid("([{}])") << endl;   // true
    cout << isValid("(((") << endl;      // false
    return 0;
}

```

---

## 🔹 Key Takeaways

- Use **stack** to store unmatched opening brackets.
- Closing brackets must match the **top of the stack**.
- **Empty stack** at the end → string is balanced.
- Time Complexity → `O(n)`
- Space Complexity → `O(n)` (stack for unmatched brackets)