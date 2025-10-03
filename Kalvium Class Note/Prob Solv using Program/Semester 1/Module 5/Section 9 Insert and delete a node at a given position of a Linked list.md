# 🧠 Concept Overview

A **Linked List** is a linear data structure where elements (called **nodes**) are connected using pointers (references).  
Each **node** contains:

- **data** → stores the actual value
- **next** → reference (or pointer) to the next node

Unlike arrays, linked lists do not have a fixed size, and elements are not stored contiguously in memory.

---

# 📍 Operations: Insertion & Deletion at a Given Position

You can perform two major operations:

1. **Insert a node at position `i`**
2. **Delete a node from position `i`**

> Positions are usually **0-indexed** (first node = position 0).

---

## ⚙️ 1. Insertion at a Given Position

### 🧩 Algorithm

1. **Create the new node** with the data you want to insert.
2. If `i == 0`, make the new node’s `next` point to the current head and update `head` to the new node.
3. Otherwise:
    - Traverse the list to reach the **(i-1)th node**.
    - Set new node’s `next` to the `next` of that node.
    - Update that node’s `next` pointer to the new node.
4. Return the head of the updated list.

---

## ⚙️ 2. Deletion at a Given Position

### 🧩 Algorithm

1. If the list is empty (`head == null`), do nothing.
2. If `i == 0`, move head to `head.next` and delete the original head.
3. Otherwise:
    - Traverse to **(i-1)th node**.
    - Let `temp = prev.next` (the node to delete).
    - Update `prev.next = temp.next` (skips the deleted node).
    - Free or remove `temp`.
4. Return the updated head.

---

# 🧮 Universal Code (Python | Java | C++)

Below are equivalent implementations in all three languages.  
Comments explain each step clearly.

---

## 🐍 Python Implementation

```python
class Node:  
	def **init**(self, data):  
	self.data = data  
	self.next = None

	def insert_at_position(head, data, pos):  
	new_node = Node(data) # Step 1: Create a new node
```

---

## ☕ Java Implementation

class Node {  
int data;  
Node next;

`Node(int data) {     this.data = data;     this.next = null; }`

}

public class LinkedListOps {

`public static Node insertAtPosition(Node head, int data, int pos) {     Node newNode = new Node(data); // Step 1: Create new node      // Case 1: Insert at head     if (pos == 0) {         newNode.next = head;         return newNode;     }      // Step 2: Traverse to (pos-1)th node     Node current = head;     int count = 0;     while (current != null && count < pos - 1) {         current = current.next;         count++;     }      // If position out of range     if (current == null)         return head;      // Step 3: Insert node     newNode.next = current.next;     current.next = newNode;      return head; }  public static Node deleteAtPosition(Node head, int pos) {     if (head == null)         return null;      // Case 1: Delete head     if (pos == 0) {         head = head.next;         return head;     }      // Step 2: Traverse to (pos-1)th node     Node current = head;     int count = 0;     while (current.next != null && count < pos - 1) {         current = current.next;         count++;     }      // If position out of range     if (current.next == null)         return head;      // Step 3: Delete node     current.next = current.next.next;     return head; }`

}

---

## 💻 C++ Implementation

#include <iostream>  
using namespace std;

class Node {  
public:  
int data;  
Node* next;

`Node(int val) {     data = val;     next = NULL; }`

};

// Function to insert a node at a given position  
Node* insertAtPosition(Node* head, int data, int pos) {  
Node* newNode = new Node(data); // Step 1: Create new node

`// Case 1: Insert at head if (pos == 0) {     newNode->next = head;     return newNode; }  // Step 2: Traverse to (pos-1)th node Node* current = head; int count = 0; while (current != NULL && count < pos - 1) {     current = current->next;     count++; }  // If position out of range if (current == NULL)     return head;  // Step 3: Insert new node newNode->next = current->next; current->next = newNode;  return head;`

}

// Function to delete node at given position  
Node* deleteAtPosition(Node* head, int pos) {  
if (head == NULL)  
return NULL;

`// Case 1: Delete head if (pos == 0) {     Node* temp = head;     head = head->next;     delete temp;     return head; }  // Step 2: Traverse to (pos-1)th node Node* current = head; int count = 0; while (current->next != NULL && count < pos - 1) {     current = current->next;     count++; }  // If position out of range if (current->next == NULL)     return head;  // Step 3: Delete node Node* temp = current->next; current->next = temp->next; delete temp;  return head;`

}

---

# 🧠 Explanation of Each Step

|Step|Action|Description|
|---|---|---|
|1|Create node|Allocate memory and set data.|
|2|Special case|Handle position = 0 (head insert/delete).|
|3|Traverse|Move through list until `(pos-1)` node.|
|4|Pointer update (Insert)|Connect new node’s next to current.next.|
|5|Pointer update (Delete)|Skip deleted node by linking prev to next.|
|6|Edge check|Avoid out-of-bound errors when position is invalid.|
|7|Return head|Return possibly updated head after operation.|

---

# 🧩 Edge Cases

1. **Empty list (head = null)** — handle gracefully.
    
2. **Insert at position 0** — becomes new head.
    
3. **Delete at position 0** — next node becomes new head.
    
4. **Position > length of list** — do nothing.
    
5. **Negative position** — invalid, return list as-is.
    

---

# 📘 Summary

- Use traversal to reach the desired position.
    
- Always handle special case `pos = 0`.
    
- Update `next` pointers carefully.
    
- Deletion requires freeing memory (C++), or just removing reference (Java/Python).