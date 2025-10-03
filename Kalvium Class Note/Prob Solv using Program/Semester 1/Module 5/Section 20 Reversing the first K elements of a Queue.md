# 📒 Notes: Reversing the First K Elements of a Queue

---

## 🔹 Problem Statement

Given a **queue** of `N` integers and an integer `K`, reverse the **first K elements** of the queue while leaving the remaining elements in the same relative order.

**Allowed Queue Operations:**

- `enqueue(x)` → Add x to the rear
- `dequeue()` → Remove element from the front
- `size()` → Number of elements in queue
- `front()` → Element at the front

**Input:**

- First line: `N K` → total elements and number of elements to reverse
- Second line: `N` space-separated integers → elements of the queue (front first)

**Output:**

- Modified queue with first K elements reversed, printed as **space-separated integers**

---

### Example 1

**Input:**

```
5 3 1 2 3 4 5
```

**Output:**

```
3 2 1 4 5
```

**Explanation:**

- First 3 elements `[1,2,3]` reversed → `[3,2,1]`
- Remaining `[4,5]` stays in order → final queue `[3,2,1,4,5]`

---

### Example 2

**Input:**

```
4 4 4 3 2 1
```

**Output:**

```
1 2 3 4
```

**Explanation:**

- K = N → reverse entire queue

---

## 🔹 Approach

1. **Edge Cases:**
    - If `K = 0` → nothing to reverse
    - If `K = N` → reverse entire queue
2. **Reverse First K Elements:**
    - Use a **stack** to reverse order
    - **Step 1:** Dequeue first K elements from queue and push onto stack
    - **Step 2:** Pop elements from stack and enqueue back to queue → first K elements reversed
3. **Maintain Remaining Elements:**
    - Remaining `N - K` elements are already at the back
    - Dequeue each and enqueue it back to maintain original order
4. **Return Modified Queue**

**Time Complexity:** `O(N)`  
**Space Complexity:** `O(K)` (stack for first K elements)

---
```embed
title: "Reverse First K elements of Queue   || GeeksforGeeks || Problem of the Day || Must Watch"
image: "https://i.ytimg.com/vi/W3cQf2me9lg/maxresdefault.jpg"
description: "Reverse First K elements of Queue || GeeksforGeeks || Problem of the Day || Must WatchJoin us at telegram: https://t.me/placement_phodenge For all GFG course..."
url: "https://youtu.be/W3cQf2me9lg"
favicon: ""
aspectRatio: "56.25"
```

## 🔹 Code Implementations

---

### ✅ Python Implementation

```python
from collections import deque

def modifyQueue(queue, K):
    stack = []
    
    # Step 1: Push first K elements onto stack
    for _ in range(K):
        stack.append(queue.popleft())
    
    # Step 2: Enqueue back the reversed elements
    while stack:
        queue.append(stack.pop())
    
    # Step 3: Move remaining N-K elements to back to maintain order
    size = len(queue)
    for _ in range(size - K):
        queue.append(queue.popleft())
    
    return queue

# Input
N, K = map(int, input().split())
q = deque(map(int, input().split()))
q = modifyQueue(q, K)
print(*q)

```

---

### ✅ Java Implementation

```java
import java.util.*;
public class ReverseKQueue {
    public static Queue<Integer> modifyQueue(Queue<Integer> q, int K) {
        Stack<Integer> stack = new Stack<>();
        
        // Step 1: Push first K elements onto stack
        for (int i = 0; i < K; i++) {
            stack.push(q.poll());
        }
        
        // Step 2: Enqueue back the reversed elements
        while (!stack.isEmpty()) {
            q.add(stack.pop());
        }
        
        // Step 3: Move remaining N-K elements to back
        int size = q.size();
        for (int i = 0; i < size - K; i++) {
            q.add(q.poll());
        }
        
        return q;
    }
    
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int N = sc.nextInt();
        int K = sc.nextInt();
        Queue<Integer> q = new LinkedList<>();
        for (int i = 0; i < N; i++) {
            q.add(sc.nextInt());
        }
        q = modifyQueue(q, K);
        for (int num : q) System.out.print(num + " ");
    }
}

```

---

### ✅ C++ Implementation

```cpp
#include <iostream>
#include <queue>
#include <stack>
using namespace std;

queue<int> modifyQueue(queue<int> q, int K) {
    stack<int> st;
    
    // Step 1: Push first K elements to stack
    for (int i = 0; i < K; i++) {
        st.push(q.front());
        q.pop();
    }
    
    // Step 2: Enqueue back reversed elements
    while (!st.empty()) {
        q.push(st.top());
        st.pop();
    }
    
    // Step 3: Move remaining N-K elements to back
    int size = q.size();
    for (int i = 0; i < size - K; i++) {
        q.push(q.front());
        q.pop();
    }
    
    return q;
}

int main() {
    int N, K;
    cin >> N >> K;
    queue<int> q;
    for (int i = 0; i < N; i++) {
        int x; cin >> x;
        q.push(x);
    }
    q = modifyQueue(q, K);
    while(!q.empty()) {
        cout << q.front() << " ";
        q.pop();
    }
}

```

---

## 🔹 Key Takeaways

- Use **stack** to reverse the first K elements efficiently.
- Remaining elements can be rotated to maintain order → simple `dequeue` and `enqueue`.
- Time Complexity → `O(N)`
- Space Complexity → `O(K)` for stack