# 📒 Notes: Min Stack

---

## 🔹 Problem Statement

Implement a **stack** that supports three operations **efficiently**:

1. **Push x** → add element `x` to the stack.
2. **Pop** → remove and return the top element (return -1 if stack is empty).
3. **GetMin** → return the minimum element in the stack (return -1 if stack is empty).

**Goal:** Retrieve minimum element in **O(1) time**.

---

### Example 1

**Input:**

```
6 1 3 1 2 1 1 3 2 3
```

**Output:**

```
1 2 1
```

**Explanation:**

- Push 3 → stack: [3], minStack: [3]
- Push 2 → stack: [3,2], minStack: [3,2]
- Push 1 → stack: [3,2,1], minStack: [3,2,1]
- GetMin → 1
- Pop → 1, also pop from minStack → stack: [3,2], minStack: [3,2] → print 1
- GetMin → 2

---

### Example 2

**Input:**

```
3 1 4 3 2
```

**Output:**

```
4 4
```

---

## 🔹 Approach: Using Two Stacks

**Idea:**
- Maintain **two stacks**:
    1. `stack` → stores all elements
    2. `minStack` → stores minimum elements seen so far

**Operations:**

1. **Push x:**
    - Push x onto `stack`
    - If `minStack` is empty **or** x ≤ minStack.top → push x onto `minStack`
2. **Pop:**
    - If `stack` is empty → print -1
    - Else, pop from `stack`
    - If popped element = minStack.top → also pop `minStack`
    - Print popped value
3. **GetMin:**
    - If `minStack` is empty → print -1
    - Else → print minStack.top

**Time Complexity:** `O(1)` per operation  
**Space Complexity:** `O(n)` for two stacks

---
```embed
title: "Design Min Stack - Amazon Interview Question - Leetcode 155 - Python"
image: "https://i.ytimg.com/vi/qkLl7nAwDPo/maxresdefault.jpg"
description: "🚀 https://neetcode.io/ - A better way to prepare for Coding Interviews🐦 Twitter: https://twitter.com/neetcode1🥷 Discord: https://discord.gg/ddjKRXPqtk🐮 S..."
url: "https://youtu.be/qkLl7nAwDPo"
favicon: ""
aspectRatio: "56.25"
```

## 🔹 Code Implementations

---

### ✅ Python Implementation

```python
q = int(input())
stack = []
minStack = []
res = []

for _ in range(q):
    command = input().split()
    
    if command[0] == '1':  # push x
        x = int(command[1])
        stack.append(x)
        if not minStack or x <= minStack[-1]:
            minStack.append(x)
    elif command[0] == '2':  # pop
        if not stack:
            res.append(-1)
        else:
            top = stack.pop()
            if minStack and top == minStack[-1]:
                minStack.pop()
            res.append(top)
    elif command[0] == '3':  # getMin
        if not minStack:
            res.append(-1)
        else:
            res.append(minStack[-1])

print(" ".join(map(str, res)))

```

---

### ✅ Java Implementation

```java

```

---

### ✅ C++ Implementation

```cpp
#include <iostream>
#include <stack>
using namespace std;

int main() {
    int q;
    cin >> q;
    stack<long long> st, minSt;
    
    while(q--) {
        int type;
        cin >> type;
        if(type == 1) { // push
            long long x;
            cin >> x;
            st.push(x);
            if(minSt.empty() || x <= minSt.top())
                minSt.push(x);
        } else if(type == 2) { // pop
            if(st.empty()) cout << -1 << " ";
            else {
                long long top = st.top();
                st.pop();
                if(!minSt.empty() && top == minSt.top()) minSt.pop();
                cout << top << " ";
            }
        } else if(type == 3) { // getMin
            if(minSt.empty()) cout << -1 << " ";
            else cout << minSt.top() << " ";
        }
    }
}

```

---

## 🔹 Key Takeaways

- Use **two stacks** → main stack for elements, minStack for tracking minimums.
- Efficient retrieval of minimum → **O(1)** per operation.
- Edge cases → empty stack must return -1.
- Space Complexity → **O(n)**, Time Complexity → **O(1) per query**.