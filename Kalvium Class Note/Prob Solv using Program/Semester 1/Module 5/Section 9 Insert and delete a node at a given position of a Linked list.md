# 📒 Notes: Insert & Delete Node at a Given Position in a Linked List

## 🔹 What is a Linked List?

- A **Linked List** is a linear data structure where elements (called **nodes**) are connected using **pointers/references**.
- Each **node** has:
    1. **Data** (the value stored)
    2. **Next** (pointer/reference to the next node)
- Unlike arrays, linked lists are **dynamic** in size and allow efficient insertion/deletion.

---

## 🔹 Operations Required

We need to implement **two operations**:

1. **Insert at a given position `i`**  
    Example: Insert `50` at position `2` in list `10 → 20 → 30` → `10 → 20 → 50 → 30`
2. **Delete at a given position `i`**  
    Example: Delete at position `2` in list `10 → 20 → 50 → 30` → `10 → 20 → 30`


---

## 🔹 Steps for Insertion

1. **If inserting at position 0 (head):**
    - Create a new node.
    - Point new node’s `next` to current head.
    - Update head to new node.
2. **If inserting at position i (i > 0):**
    - Traverse until you reach `i-1`th node.
    - Create new node.
    - Point new node’s `next` to `i`th node.
	- Update `(i-1)`th node’s `next` to new node.

```embed
title: "Single Linked List (Inserting a Node at a Certain Position)"
image: "https://i.ytimg.com/vi/0hGxILnKvJk/maxresdefault.jpg"
description: "Data Structures: Inserting a Node at a certain position in a Singly Linked ListTopics discussed:1) Adding a node in a Singly Linked List to a certain positio..."
url: "https://youtu.be/0hGxILnKvJk"
favicon: ""
aspectRatio: "56.25"
```

---

## 🔹 Steps for Deletion

1. **If deleting at position 0 (head):**
    - Move head to `head.next`.
    - Free the old head.
2. **If deleting at position i (i > 0):**
    - Traverse until you reach `i-1`th node.
    - Update `(i-1)`th node’s `next` to `i+1`th node.
    - Free the `i`th node.

```embed
title: "Single Linked List (Deleting the Node at a Particular Position)"
image: "https://i.ytimg.com/vi/f1r_jxCyOl0/maxresdefault.jpg"
description: "Data Structures: Deleting the Node of a Singly Linked List at a Specified Position.Topics discussed:1) C program to delete the node of a singly linked list p..."
url: "https://youtu.be/f1r_jxCyOl0"
favicon: ""
aspectRatio: "56.25"
```

---

# 🔹 Code Implementations (Universal)

---

## ✅ Python Implementation

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None
        
# Insert at position i
def insert_at_position(head, data, i):
    new_node = Node(data)

    # Case 1: Insert at head (position 0)
    if i == 0:
        new_node.next = head
        return new_node

    # Case 2: Insert at other positions
    temp = head
    count = 0
    while temp is not None and count < i - 1:
        temp = temp.next
        count += 1

    if temp is None:
        print("Position out of range!")
        return head

    new_node.next = temp.next
    temp.next = new_node
    return head

# Delete at position i
def delete_at_position(head, i):
    if head is None:
        return None

    # Case 1: Delete head
    if i == 0:
        return head.next

    temp = head
    count = 0
    while temp is not None and count < i - 1:
        temp = temp.next
        count += 1

    if temp is None or temp.next is None:
        print("Position out of range!")
        return head

    temp.next = temp.next.next
    return head

# Helper to print linked list
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

public class LinkedListOps {
    
    // Insert at position i
    public static Node insertAtPosition(Node head, int data, int i) {
        Node newNode = new Node(data);

        // Case 1: Insert at head
        if (i == 0) {
            newNode.next = head;
            return newNode;
        }

        Node temp = head;
        int count = 0;

        // Traverse to (i-1)th node
        while (temp != null && count < i - 1) {
            temp = temp.next;
            count++;
        }

        if (temp == null) {
            System.out.println("Position out of range!");
            return head;
        }

        newNode.next = temp.next;
        temp.next = newNode;
        return head;
    }

    // Delete at position i
    public static Node deleteAtPosition(Node head, int i) {
        if (head == null) return null;

        // Case 1: Delete head
        if (i == 0) return head.next;

        Node temp = head;
        int count = 0;

        while (temp != null && count < i - 1) {
            temp = temp.next;
            count++;
        }

        if (temp == null || temp.next == null) {
            System.out.println("Position out of range!");
            return head;
        }

        temp.next = temp.next.next;
        return head;
    }

    // Print Linked List
    public static void printList(Node head) {
        Node temp = head;
        while (temp != null) {
            System.out.print(temp.data + " → ");
            temp = temp.next;
        }
        System.out.println("null");
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

// Insert at position i
Node* insertAtPosition(Node* head, int data, int i) {
    Node* newNode = new Node(data);

    // Case 1: Insert at head
    if (i == 0) {
        newNode->next = head;
        return newNode;
    }

    Node* temp = head;
    int count = 0;

    while (temp != nullptr && count < i - 1) {
        temp = temp->next;
        count++;
    }

    if (temp == nullptr) {
        cout << "Position out of range!" << endl;
        return head;
    }

    newNode->next = temp->next;
    temp->next = newNode;
    return head;
}

// Delete at position i
Node* deleteAtPosition(Node* head, int i) {
    if (head == nullptr) return nullptr;

    // Case 1: Delete head
    if (i == 0) {
        Node* temp = head;
        head = head->next;
        delete temp;
        return head;
    }

    Node* temp = head;
    int count = 0;

    while (temp != nullptr && count < i - 1) {
        temp = temp->next;
        count++;
    }

    if (temp == nullptr || temp->next == nullptr) {
        cout << "Position out of range!" << endl;
        return head;
    }

    Node* nodeToDelete = temp->next;
    temp->next = nodeToDelete->next;
    delete nodeToDelete;

    return head;
}

// Print Linked List
void printList(Node* head) {
    while (head != nullptr) {
        cout << head->data << " → ";
        head = head->next;
    }
    cout << "NULL" << endl;
}

```

---

# 🔹 Key Takeaways

- Always **handle special cases**:
    - Insertion/deletion at head (`i=0`)
    - Position **out of range**
    - Empty list (`head == null`)
- Time Complexity:
    - Traversal: **O(n)**
    - Insertion/Deletion: **O(1)** (after traversal)
- Linked list gives flexibility but needs careful **pointer/reference updates**.