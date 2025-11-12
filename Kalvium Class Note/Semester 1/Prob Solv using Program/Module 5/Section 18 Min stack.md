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
class Solution:
    def __init__(self):
        self.s = []
        self.minstack = []
        
#Answer---

    def push(self, x):
        self.s.append(x)
        if not self.minstack or x <= self.minstack[-1]:
            self.minstack.append(x)
    def pop(self):
        if not self.s:
            return -1
        top = self.s.pop()
        if top == self.minstack[-1]:
            self.minstack.pop()
        return top
    def getMin(self):
        if not self.minstack:
            return -1
        return self.minstack[-1]

#Answe---

if __name__ == "__main__":
    q = int(input())
    ob = Solution()

    for _ in range(q):
        parts = input().split()
        qt = int(parts[0])
        if qt == 1:
            ob.push(int(parts[1]))
        elif qt == 2:
            print(ob.pop(), end=" ")
        elif qt == 3:
            print(ob.getMin(), end=" ")


```

---

### ✅ Java Implementation

```java
import java.util.Scanner;
import java.util.Stack;

class Solution {
    private Stack<Integer> s;
    private Stack<Integer> minstack;
    
    Solution() {
        s = new Stack<>();
        minstack = new Stack<>();
    }
    //Answer ---
    
    int getMin() {
        if (minstack.isEmpty()) return -1;
        return minstack.peek();
    }
    int pop() {
        if (s.isEmpty()) return -1;
        int top = s.pop();
        if (top == minstack.peek()) minstack.pop();
        return top;
    }
    void push(int x) {
        s.push(x);
        if (minstack.isEmpty() || x <= minstack.peek()) minstack.push(x);
    }
    
    //Answer---
    
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int q = sc.nextInt();
        Solution ob = new Solution();
        while (q-- > 0) {
            int qt = sc.nextInt();
            if (qt == 1) {
                int att = sc.nextInt();
                ob.push(att);
            } else if (qt == 2) {
                System.out.print(ob.pop() + " ");
            } else if (qt == 3) {
                System.out.print(ob.getMin() + " ");
            }
        }
        sc.close();
    }
}

```

---

### ✅ C++ Implementation

```cpp
#include <iostream>
#include <stack>
using namespace std;

class Solution {
    stack<int> s;
    stack<int> minstack;
    
//Answer---

public:
    void push(int x) {
        s.push(x);
        if (minstack.empty() || x <= minstack.top())
            minstack.push(x);
    }
    int pop() {
        if (s.empty())
            return -1;
        int top = s.top();
        s.pop();
        if (top == minstack.top())
            minstack.pop();
        return top;
    }
    int getMin() {
        if (minstack.empty())
            return -1;
        return minstack.top();
    }
};

//Answer---

int main() {
    int q;
    cin >> q;
    Solution ob;

    while (q--) {
        int qt;
        cin >> qt;
        if (qt == 1) {
            int att;
            cin >> att;
            ob.push(att);
        } else if (qt == 2) {
            cout << ob.pop() << " ";
        } else if (qt == 3) {
            cout << ob.getMin() << " ";
        }
    }
    return 0;
}

```

---

## 🔹 Key Takeaways

- Use **two stacks** → main stack for elements, minStack for tracking minimums.
- Efficient retrieval of minimum → **O(1)** per operation.
- Edge cases → empty stack must return -1.
- Space Complexity → **O(n)**, Time Complexity → **O(1) per query**.