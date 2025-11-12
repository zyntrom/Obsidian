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
def addTwoLists(first, second):
    # Step 1: Convert first list to number
    num1 = 0
    while first:
        num1 = num1 * 10 + first.data
        first = first.next
    # Step 2: Convert second list to number
    num2 = 0
    while second:
        num2 = num2 * 10 + second.data
        second = second.next
    # Step 3: Add both numbers
    total = num1 + num2
    # Step 4: Convert total to linked list
    if total == 0:
        return Node(0)
    head = None
    tail = None
    for ch in str(total):
        digit = int(ch)
        newNode = Node(digit)
        if not head:
            head = newNode
            tail = newNode
        else:
            tail.next = newNode
            tail = tail.next
    return head


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

public static Node addTwoLists(Node first, Node second) {
    // Step 1: Convert first linked list to number
    long num1 = 0;
    while (first != null) {
        num1 = num1 * 10 + first.data;
        first = first.next;
    }
    // Step 2: Convert second linked list to number
    long num2 = 0;
    while (second != null) {
        num2 = num2 * 10 + second.data;
        second = second.next;
    }
    // Step 3: Add the two numbers
    long sum = num1 + num2;

    // Step 4: Convert the sum back into a linked list
    // Edge case: if sum = 0
    if (sum == 0) {
        return new Node(0);
    }
    // Create list from digits of sum
    Node head = null;
    Node tail = null;
    // Convert number to linked list
    String sumStr = Long.toString(sum);
    for (int i = 0; i < sumStr.length(); i++) {
        int digit = sumStr.charAt(i) - '0';
        Node newNode = new Node(digit);
        if (head == null) {
            head = newNode;
            tail = newNode;
        } else {
            tail.next = newNode;
            tail = tail.next;
        }
    }
    return head;
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


Node* addTwoLists(Node* first, Node* second) {
    // Step 1: Convert first list to number
    long long num1 = 0;
    while (first != nullptr) {
        num1 = num1 * 10 + first->data;
        first = first->next;
    }
    // Step 2: Convert second list to number
    long long num2 = 0;
    while (second != nullptr) {
        num2 = num2 * 10 + second->data;
        second = second->next;
    }
    // Step 3: Add both numbers
    long long sum = num1 + num2;
    // Step 4: Convert sum back to linked list
    if (sum == 0) return new Node(0);
    string s = to_string(sum);
    Node* head = nullptr;
    Node* tail = nullptr;
    for (char c : s) {
        int digit = c - '0';
        Node* newNode = new Node(digit);
        if (!head) {
            head = newNode;
            tail = newNode;
        } else {
            tail->next = newNode;
            tail = newNode;
        }
    }
    return head;
}

```

---

# 🔹 Key Takeaways

- Reverse the linked lists → **addition easier from least significant digit**.
- Maintain a **carry** like elementary addition.
- Use a **dummy node** to simplify list construction.
- Reverse the result at the end to restore original order.
- Works for **different length lists** and carries over multiple digits.