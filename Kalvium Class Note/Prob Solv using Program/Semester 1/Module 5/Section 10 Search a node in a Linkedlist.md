# 📒 Notes: Search a Node in a Linked List

---

## 🔹 Problem Statement

We are given:

- A **singly linked list**
- A value `x`

We must check **whether `x` exists in the linked list**.

- If found → return `true`
- If not found → return `false`

---

## 🔹 Example

Input:

```
head = 1 → 2 → 3 → 4 → null, x = 3
```

Output:

```
true
```

Input:

```
head = 7 → 8 → 2 → 1 → null, x = 5
```

Output:

```
false
```

---

## 🔹 Approach (Step-by-Step)

This is basically a **Linear Search** applied to a linked list.

1. Start from the **head node**.
2. Traverse the list one node at a time.
3. At each node, check:
    - If `node.data == x`, return **true** immediately.
4. If you reach the end (`null`) without finding `x`, return **false**.

---

## 🔹 Time & Space Complexity

- **Time Complexity:** `O(n)` (we may check all `n` nodes in worst case).
- **Space Complexity:** `O(1)` (no extra memory, just traversal).

---

# 🔹 Universal Code Implementations

---

## ✅ Python Implementation

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

def search_in_linkedlist(head, x):
    temp = head
    while temp is not None:
        if temp.data == x:
            return True
        temp = temp.next
    return False

# Helper to create and print linked list
def print_list(head):
    while head:
        print(head.data, end=" → ")
        head = head.next
    print("None")

# Example usage:
# head = Node(1)
# head.next = Node(2)
# head.next.next = Node(3)
# print(search_in_linkedlist(head, 3))  # True
# print(search_in_linkedlist(head, 5))  # False

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

public class LinkedListSearch {
    
    public static boolean search(Node head, int x) {
        Node temp = head;
        while (temp != null) {
            if (temp.data == x) {
                return true;
            }
            temp = temp.next;
        }
        return false;
    }

    // Helper to print list
    public static void printList(Node head) {
        Node temp = head;
        while (temp != null) {
            System.out.print(temp.data + " → ");
            temp = temp.next;
        }
        System.out.println("null");
    }

    public static void main(String[] args) {
        Node head = new Node(7);
        head.next = new Node(8);
        head.next.next = new Node(2);
        head.next.next.next = new Node(1);

        System.out.println(search(head, 5)); // false
        System.out.println(search(head, 2)); // true
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

// Search function
bool search(Node* head, int x) {
    Node* temp = head;
    while (temp != nullptr) {
        if (temp->data == x) {
            return true;
        }
        temp = temp->next;
    }
    return false;
}

// Helper to print list
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

    cout << (search(head, 3) ? "true" : "false") << endl; // true
    cout << (search(head, 5) ? "true" : "false") << endl; // false

    return 0;
}

```

---

# 🔹 Key Takeaways

- Searching in a linked list is just **linear traversal**.
- Unlike arrays, **you can’t use binary search** because linked lists don’t have **random access**.
- Always start from `head` and traverse until `null`.
- Return `true` as soon as you find the element → this avoids unnecessary traversal.