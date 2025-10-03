# 📒 Notes: Add Two Numbers Represented as Linked Lists

---

## 🔹 Problem Statement

- You are given **two linked lists** representing two decimal numbers.
- Each node contains a single digit.
- The digits are stored in **left-to-right order** (most significant digit first).
- Return a **linked list representing the sum**.

### Example 1

Input:

```
List1: 1 → 9 → 0  List2: 2 → 5
```

Output:

```
2 → 1 → 5
```

Explanation: 190 + 25 = 215 → represented as linked list.

### Example 2

Input:

```
List1: 4 → 5  List2: 3 → 4 → 5
```

Output:

```
3 → 9 → 0
```

Explanation: 45 + 345 = 390 → represented as linked list.

---

## 🔹 Approach

**Step 1: Reverse Both Lists**

- Addition is easier from **least significant digit** → rightmost node.
- Reverse both linked lists first.

**Step 2: Initialize Pointers and Carry**

- Use a **dummy node** to start the result list.
- Initialize `carry = 0`.
- Use a pointer `point` to build the new list.

**Step 3: Add Digits**

- Loop until both lists are exhausted and `carry = 0`.
- At each step:
    1. Compute sum = `carry + (digit1) + (digit2)`.
    2. Update `carry = sum // 10`.
    3. Create a new node with value `sum % 10`.
    4. Move `point` to this new node.
    5. Move input list pointers forward.

**Step 4: Reverse the Result List**

- Reverse the sum list to get **most significant digit first**.

---

## 🔹 Time & Space Complexity

- **Time Complexity:** `O(max(N, M))` for reversing + addition
- **Space Complexity:** `O(max(N, M))` for new linked list

---

# 🔹 Code Implementations

---

## ✅ Python Implementation

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

# Function to reverse a linked list
def reverse(head):
    prev = None
    curr = head
    while curr:
        next_node = curr.next
        curr.next = prev
        prev = curr
        curr = next_node
    return prev

def addTwoLists(l1, l2):
    # Step 1: Reverse both lists
    l1 = reverse(l1)
    l2 = reverse(l2)
    
    dummy = Node(0)
    point = dummy
    carry = 0
    
    # Step 2: Add digits
    while l1 or l2 or carry:
        x = l1.data if l1 else 0
        y = l2.data if l2 else 0
        total = x + y + carry
        carry = total // 10
        point.next = Node(total % 10)
        point = point.next
        if l1: l1 = l1.next
        if l2: l2 = l2.next
    
    # Step 3: Reverse the result
    return reverse(dummy.next)

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

public class AddTwoNumbersLinkedList {

    // Reverse function
    public static Node reverse(Node head) {
        Node prev = null;
        Node curr = head;
        while (curr != null) {
            Node nextNode = curr.next;
            curr.next = prev;
            prev = curr;
            curr = nextNode;
        }
        return prev;
    }

    // Add two lists
    public static Node addTwoLists(Node l1, Node l2) {
        l1 = reverse(l1);
        l2 = reverse(l2);
        
        Node dummy = new Node(0);
        Node point = dummy;
        int carry = 0;
        
        while (l1 != null || l2 != null || carry != 0) {
            int x = (l1 != null) ? l1.data : 0;
            int y = (l2 != null) ? l2.data : 0;
            int sum = x + y + carry;
            carry = sum / 10;
            point.next = new Node(sum % 10);
            point = point.next;
            
            if (l1 != null) l1 = l1.next;
            if (l2 != null) l2 = l2.next;
        }
        
        return reverse(dummy.next);
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

// Reverse linked list
Node* reverse(Node* head) {
    Node* prev = nullptr;
    Node* curr = head;
    while (curr) {
        Node* nextNode = curr->next;
        curr->next = prev;
        prev = curr;
        curr = nextNode;
    }
    return prev;
}

// Add two lists
Node* addTwoLists(Node* l1, Node* l2) {
    l1 = reverse(l1);
    l2 = reverse(l2);

    Node* dummy = new Node(0);
    Node* point = dummy;
    int carry = 0;

    while (l1 || l2 || carry) {
        int x = l1 ? l1->data : 0;
        int y = l2 ? l2->data : 0;
        int sum = x + y + carry;
        carry = sum / 10;
        point->next = new Node(sum % 10);
        point = point->next;

        if (l1) l1 = l1->next;
        if (l2) l2 = l2->next;
    }

    Node* result = reverse(dummy->next);
    delete dummy;
    return result;
}

```

---

# 🔹 Key Takeaways

- Reverse the linked lists → **addition easier from least significant digit**.
- Maintain a **carry** like elementary addition.
- Use a **dummy node** to simplify list construction.
- Reverse the result at the end to restore original order.
- Works for **different length lists** and carries over multiple digits.