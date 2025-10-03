# 📒 Notes: Reverse a Linked List

---

## 🔹 Problem Statement

Given the head of a singly linked list, reverse it and return the new head.

### Example

Input:

```
head = [1, 2, 3, 4, 5]
```

Output:

```
5, 4, 3, 2, 1
```

---

## 🔹 Concept / Approach

To reverse a linked list:

- We need to **change the direction of pointers** so that each node points to its **previous node** instead of its next node.

We use **three pointers**:

1. `prev` → initially `None` (previous node)
2. `curr` → initially `head` (current node)
3. `next` → to temporarily store the next node

### Steps:

1. Store `next = curr.next` (save next node before breaking link).
2. Change link: `curr.next = prev` (reverse direction).
3. Move `prev` to `curr`.
4. Move `curr` to `next`.
5. Repeat until `curr == null`.
6. At the end, `prev` becomes the new **head** of the reversed list.

---

## 🔹 Time & Space Complexity

- **Time Complexity:** `O(n)` (we traverse the list once).
- **Space Complexity:** `O(1)` (only using a few extra pointers).

---

# 🔹 Code Implementations

---

## ✅ Python Implementation

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

def reverse_linkedlist(head):
    prev = None
    curr = head
    
    while curr is not None:
        next_node = curr.next   # Save next node
        curr.next = prev        # Reverse the link
        prev = curr             # Move prev forward
        curr = next_node        # Move curr forward
    
    return prev  # New head

# Helper to print list
def print_list(head):
    while head:
        print(head.data, end=" → ")
        head = head.next
    print("None")

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

public class LinkedListReverse {
    public static Node reverse(Node head) {
        Node prev = null;
        Node curr = head;

        while (curr != null) {
            Node nextNode = curr.next; // Save next node
            curr.next = prev;          // Reverse the link
            prev = curr;               // Move prev forward
            curr = nextNode;           // Move curr forward
        }
        return prev; // New head
    }

    public static void printList(Node head) {
        Node temp = head;
        while (temp != null) {
            System.out.print(temp.data + " → ");
            temp = temp.next;
        }
        System.out.println("null");
    }

    public static void main(String[] args) {
        Node head = new Node(1);
        head.next = new Node(2);
        head.next.next = new Node(3);

        head = reverse(head);
        printList(head); // Output: 3 → 2 → 1 → null
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

Node* reverseLinkedList(Node* head) {
    Node* prev = nullptr;
    Node* curr = head;

    while (curr != nullptr) {
        Node* nextNode = curr->next; // Save next node
        curr->next = prev;           // Reverse the link
        prev = curr;                 // Move prev forward
        curr = nextNode;             // Move curr forward
    }
    return prev; // New head
}

void printList(Node* head) {
    while (head != nullptr) {
        cout << head->data << " → ";
        head = head->next;
    }
    cout << "NULL" << endl;
}

int main() {
    Node* head = new Node(1);
    head->next = new Node(2);
    head->next->next = new Node(3);

    head = reverseLinkedList(head);
    printList(head); // Output: 3 → 2 → 1 → NULL
    return 0;
}

```

---

# 🔹 Key Takeaways

- Reversing a linked list is an **iterative pointer manipulation problem**.
    
- Always **save next node before breaking the link** (`next_node = curr.next`).
    
- At the end, **prev becomes the new head**.
    
- Time → `O(n)` | Space → `O(1)`