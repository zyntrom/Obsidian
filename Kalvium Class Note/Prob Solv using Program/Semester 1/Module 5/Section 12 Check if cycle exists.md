# 📒 Notes: Check if Cycle Exists in a Linked List

---

## 🔹 Problem Statement

Given the head of a linked list, determine if the list contains a **cycle**.

- Return `true` if there is a cycle.
- Return `false` otherwise.

---

## 🔹 Example

Input:

```
N = 3   value[] = [1, 2, 3]   x = 2  
(last node connected to 2nd node → cycle exists)
```

Output:

```
true
```
Input:

```
head = [1, 2, 3, 4, 5] → null  (no cycle)
```

Output:

```
false
```
---

## 🔹 Approach: Floyd’s Cycle Detection Algorithm (Tortoise and Hare)

We use **two pointers**:

- `slow` → moves **1 step** at a time.
- `fast` → moves **2 steps** at a time.

### Steps:

1. If `head == null` → return `false` (empty list can’t have cycle).
2. Initialize:
    `slow = head fast = head`
3. Traverse the list:
    - Move `slow = slow.next`
    - Move `fast = fast.next.next`
4. If at any point `slow == fast` → **cycle detected** → return `true`.
5. If `fast` or `fast.next` becomes `null` → **no cycle** → return `false`.

---

## 🔹 Time & Space Complexity

- **Time Complexity:** `O(n)` (worst case: traverses whole list).
- **Space Complexity:** `O(1)` (only two pointers used).

---

```embed
title: "L14. Detect a loop or cycle in LinkedList | With proof and Intuition"
image: "https://i.ytimg.com/vi/wiOo4DC5GGA/maxresdefault.jpg"
description: "Check out TUF+:https://takeuforward.org/plus?source=youtubeFind DSA, LLD, OOPs, Core Subjects, 1000+ Premium Questions company wise, Aptitude, SQL, AI doubt ..."
url: "https://youtu.be/wiOo4DC5GGA"
favicon: ""
aspectRatio: "56.25"
```


# 🔹 Code Implementations

---

## ✅ Python Implementation

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

def has_cycle(head):
    if head is None:
        return False
    
    slow = head
    fast = head

    while fast is not None and fast.next is not None:
        slow = slow.next         # Move 1 step
        fast = fast.next.next    # Move 2 steps
        
        if slow == fast:         # Cycle detected
            return True
    
    return False  # No cycle

# Example usage:
# head = Node(1)
# head.next = Node(2)
# head.next.next = Node(3)
# head.next.next.next = head.next  # Creates a cycle
# print(has_cycle(head))  # True

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

public class LinkedListCycle {
    public static boolean hasCycle(Node head) {
        if (head == null) return false;
        
        Node slow = head;
        Node fast = head;
        while (fast != null && fast.next != null) {
            slow = slow.next;           // Move 1 step
            fast = fast.next.next;      // Move 2 steps
            
            if (slow == fast) {         // Cycle detected
                return true;
            }
        }
        return false; // No cycle
    }
    public static void main(String[] args) {
        Node head = new Node(1);
        head.next = new Node(2);
        head.next.next = new Node(3);
        head.next.next.next = head.next; // Creates cycle
        System.out.println(hasCycle(head)); // true
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

bool hasCycle(Node* head) {
    if (head == nullptr) return false;
    
    Node* slow = head;
    Node* fast = head;
    
    while (fast != nullptr && fast->next != nullptr) {
        slow = slow->next;          // Move 1 step
        fast = fast->next->next;    // Move 2 steps
        
        if (slow == fast) {         // Cycle detected
            return true;
        }
    }
    return false; // No cycle
}

int main() {
    Node* head = new Node(1);
    head->next = new Node(2);
    head->next->next = new Node(3);
    head->next->next->next = head->next; // Creates cycle

    cout << (hasCycle(head) ? "true" : "false") << endl; // true
    return 0;
}

```

---

# 🔹 Key Takeaways

- **Floyd’s Cycle Detection Algorithm (Tortoise and Hare)** is the most efficient way to detect cycles.
- If cycle exists → fast pointer eventually meets slow pointer.
- If no cycle → fast pointer reaches `null`.
- Time → `O(n)` | Space → `O(1)`