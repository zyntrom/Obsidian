# 📒 Notes: Find Middle Element in a Linked List

---

## 🔹 Problem Statement

Given the head of a singly linked list, return the **middle node**.

- If the list has **odd length**, return the single middle node.
- If the list has **even length**, return the **second middle node**.

---

## 🔹 Example

### Example 1:

Input:

```
5   (number of elements) 1 → 2 → 3 → 4 → 5
```

Output:

```
3
```

Explanation: Middle element is `3`.

---

### Example 2:

Input:

```
6 1 → 2 → 3 → 4 → 5 → 6
```

Output:

```
4
```

Explanation: Two middles (`3`, `4`), we return the **second one → 4**.

---

## 🔹 Approaches

### ✅ Method 1: Count Method

1. Traverse the list once to count the number of nodes → `n`.
2. Compute middle index = `n // 2` (integer division).
    - Works for both odd & even (automatically returns second middle for even).
3. Traverse again to reach the middle index.
4. Return that node’s value.

- **Time Complexity:** `O(n + n/2) ≈ O(n)`
- **Space Complexity:** `O(1)`

---

### ✅ Method 2: Fast and Slow Pointer (Efficient)

1. Initialize `slow = head` and `fast = head`.
2. Move `fast` by **two steps** and `slow` by **one step** at a time.
3. When `fast` reaches the end (null), `slow` will be at the **middle**.
    - For even length → `slow` ends at the **second middle** (which is required).

- **Time Complexity:** `O(n)` (single traversal).
- **Space Complexity:** `O(1)`

---

# 🔹 Code Implementations

---

## ✅ Python Implementation

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

# Method 1: Count Method
def middle_element_count(head):
    count = 0
    temp = head
    while temp:
        count += 1
        temp = temp.next
    
    mid_index = count // 2  # automatically second middle if even
    
    temp = head
    for _ in range(mid_index):
        temp = temp.next
    
    return temp.data

# Method 2: Fast and Slow Pointer
def middle_element_two_pointer(head):
    slow = head
    fast = head
    while fast and fast.next:
        slow = slow.next
        fast = fast.next.next
    return slow.data

```

---

## ✅ Java Implementation

```java
class Node {
    int data;
    Node next;
    
    Node(int data) {
        this.data = data;
        this.next = null;
    }
}

public class LinkedListMiddle {
    
    // Method 1: Count Method
    public static int middleElementCount(Node head) {
        int count = 0;
        Node temp = head;
        
        while (temp != null) {
            count++;
            temp = temp.next;
        }
        
        int midIndex = count / 2;
        temp = head;
        for (int i = 0; i < midIndex; i++) {
            temp = temp.next;
        }
        return temp.data;
    }
    
    // Method 2: Fast & Slow Pointer
    public static int middleElementTwoPointer(Node head) {
        Node slow = head;
        Node fast = head;
        
        while (fast != null && fast.next != null) {
            slow = slow.next;
            fast = fast.next.next;
        }
        return slow.data;
    }
}

```
---

## ✅ C++ Implementation

```cpp
#include <iostream>
using namespace std;

class Node {
public:
    int data;
    Node* next;
    
    Node(int data) {
        this->data = data;
        this->next = nullptr;
    }
};

// Method 1: Count Method
int middleElementCount(Node* head) {
    int count = 0;
    Node* temp = head;
    
    while (temp != nullptr) {
        count++;
        temp = temp->next;
    }
    
    int midIndex = count / 2;
    temp = head;
    for (int i = 0; i < midIndex; i++) {
        temp = temp->next;
    }
    return temp->data;
}

// Method 2: Fast & Slow Pointer
int middleElementTwoPointer(Node* head) {
    Node* slow = head;
    Node* fast = head;
    
    while (fast != nullptr && fast->next != nullptr) {
        slow = slow->next;
        fast = fast->next->next;
    }
    return slow->data;
}

```

---

# 🔹 Key Takeaways

- Two ways to find middle:
    1. **Count method** → 2 passes, simple to understand.
    2. **Fast & Slow pointer method** → 1 pass, more efficient.
- For even length lists, always return the **second middle node**.
- Time → `O(n)` | Space → `O(1)`