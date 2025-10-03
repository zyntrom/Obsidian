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
    bracket_map = {')':'(', '}':'{', ']':'['}
    
    for char in s:
        if char in '({[':
            stack.append(char)
        else:  # closing bracket
            if not stack or stack[-1] != bracket_map[char]:
                return False
            stack.pop()
    
    return len(stack) == 0

# Examples
print(isValid("()"))       # True
print(isValid("()[]{}"))   # True
print(isValid("(]"))       # False

```

---

### ✅ Java Implementation

```java
import java.util.Stack;
import java.util.HashMap;

public class BalancedParenthesis {
    public static boolean isValid(String s) {
        Stack<Character> stack = new Stack<>();
        HashMap<Character, Character> map = new HashMap<>();
        map.put(')', '(');
        map.put('}', '{');
        map.put(']', '[');
        
        for (char c : s.toCharArray()) {
            if (c == '(' || c == '{' || c == '[') {
                stack.push(c);
            } else {
                if (stack.isEmpty() || stack.pop() != map.get(c)) {
                    return false;
                }
            }
        }
        return stack.isEmpty();
    }
    
    public static void main(String[] args) {
        System.out.println(isValid("()"));       // true
        System.out.println(isValid("()[]{}"));   // true
        System.out.println(isValid("(]"));       // false
    }
}

```
---

### ✅ C++ Implementation

```cpp
#include <iostream>
#include <stack>
#include <unordered_map>
using namespace std;

bool isValid(string s) {
    stack<char> st;
    unordered_map<char, char> map = {{')','('}, {'}','{'}, {']','['}};
    
    for (char c : s) {
        if (c == '(' || c == '{' || c == '[') {
            st.push(c);
        } else {
            if (st.empty() || st.top() != map[c]) return false;
            st.pop();
        }
    }
    return st.empty();
}

int main() {
    cout << isValid("()") << endl;       // 1 (true)
    cout << isValid("()[]{}") << endl;   // 1 (true)
    cout << isValid("(]") << endl;       // 0 (false)
}

```

---

## 🔹 Key Takeaways

- Use **stack** to store unmatched opening brackets.
- Closing brackets must match the **top of the stack**.
- **Empty stack** at the end → string is balanced.
- Time Complexity → `O(n)`
- Space Complexity → `O(n)` (stack for unmatched brackets)