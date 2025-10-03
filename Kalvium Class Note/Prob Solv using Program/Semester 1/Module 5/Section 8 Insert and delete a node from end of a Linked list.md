# 🧠 [Practice] Insert and Delete a Node from End of a Linked List

## 📘 Problem Statement

Write a program to:

1. **Insert** a node at the **end** of a singly linked list.
2. **Delete** a node from the **end** of a singly linked list.

---

## 🧩 Input / Output Example

### Input:

`head = [1, 2, 3, 4] insert = 5`

### Output:

```
[1, 2, 3, 4, 5]   // after inserting 5 
[1, 2, 3, 4]      // after deleting last node
```

---

## ⚙️ Concept Overview

A **singly linked list** is made up of **nodes**, where each node contains:

- **data** → stores a value
- **next pointer** → points to the next node

For **insertion at end** and **deletion at end**, we use **pointer traversal** until we reach the **last or second-last node**.

---

## 🧱 Node Structure

### C++

```cpp
struct Node {
    int data;
    Node* next;
};

```

### Python

```python
class Node:
    def __init__(self, data=None):
        self.data = data
        self.next = None

```
### Java

```java
class Node {
    int data;
    Node next;
    Node(int data) {
        this.data = data;
        this.next = null;
    }
}

```

---

## 🔹 INSERTION AT END

### 🧠 Logic:

1. Create a new node with the given value.
2. If the list is empty (`head == null`), new node becomes the head.
3. Otherwise, **traverse** until the last node.
4. Set `last.next = new_node`.
5. Return head (unchanged).

---

### 🧮 Step-by-Step Example

Initial List → [1 → 2 → 3 → 4 → NULL]  
Insert value → `5`

- Create new node (5 → NULL)
- Traverse till node `4`
- Set `4.next = 5`
- Result → [1 → 2 → 3 → 4 → 5 → NULL]

---

### ✅ C++ Implementation

```cpp
Node* insertAtEnd(Node* head, int data) {
    Node* new_node = new Node();
    new_node->data = data;
    new_node->next = nullptr;
    if (head == nullptr) return new_node;
    Node* current = head;
    while (current->next != nullptr)
        current = current->next;
    current->next = new_node;
    return head;
}

```

---

### ✅ Python Implementation

```python
def insert_at_end(self, data):
    new_node = Node(data)
    if self.head is None:
        self.head = new_node
        return
    current = self.head
    while current.next:
        current = current.next
    current.next = new_node

```

---

### ✅ Java Implementation

```
void insertAtEnd(int data) {
    Node newNode = new Node(data);
    if (head == null) {
        head = newNode;
        return;
    }
    Node current = head;
    while (current.next != null)
        current = current.next;
    current.next = newNode;
}

```

---

## 🔹 DELETION AT END

### 🧠 Logic:

1. If list is empty → return.
2. If only one node → delete it and make `head = null`.
3. Otherwise, traverse until **second-last node**.
4. Delete the last node and set `second_last.next = null`.

---

### 🧮 Step-by-Step Example

Initial List → [1 → 2 → 3 → 4 → 5 → NULL]

1. Start traversal from `head`
2. Stop when `current.next.next == null` (here, at node `4`)
3. Delete `current.next` (node `5`)
4. Set `current.next = null`
5. Result → [1 → 2 → 3 → 4 → NULL]

---

### ✅ C++ Implementation

```cpp
Node* deleteAtEnd(Node* head) {
    if (head == nullptr) return nullptr;
    if (head->next == nullptr) {
        delete head;
        return nullptr;
    }
    Node* current = head;
    while (current->next->next != nullptr)
        current = current->next;
    delete current->next;
    current->next = nullptr;
    return head;
}

```

---

### ✅ Python Implementation

```python
def delete_at_end(self):
    if self.head is None:
        return
    if self.head.next is None:
        self.head = None
        return
    current = self.head
    while current.next.next:
        current = current.next
    del current.next
    current.next = None

```

---

### ✅ Java Implementation

```java
void deleteAtEnd() {
    if (head == null) return;
    if (head.next == null) {
        head = null;
        return;
    }
    Node current = head;
    while (current.next.next != null)
        current = current.next;
    current.next = null;  // last node removed by GC
}

```

---

## 🔹 DISPLAY FUNCTION

### 🧠 Logic:

Traverse list from `head` and print each node’s data.

### Universal Implementation

#### C++

```cpp
void display(Node* head) {
    Node* current = head;
    while (current != nullptr) {
        cout << current->data << " ";
        current = current->next;
    }
    cout << endl;
}

```

#### Python

```python
def display(self):
    current = self.head
    while current:
        print(current.data, end=" ")
        current = current.next
    print()

```

#### Java

```java
void display() {
    Node temp = head;
    while (temp != null) {
        System.out.print(temp.data + " ");
        temp = temp.next;
    }
    System.out.println();
}

```
---

## 🧮 Dry Run Example

|Step|Operation|Linked List|
|---|---|---|
|1|Insert 5|1 → 2 → 3 → 4 → 5|
|2|Delete End|1 → 2 → 3 → 4|

---

## 🧠 Summary Table

|Operation|Logic|Time Complexity|Space Complexity|
|---|---|---|---|
|Insert at End|Traverse to last node & add new node|O(n)|O(1)|
|Delete at End|Traverse to second last node & unlink last|O(n)|O(1)|

---

## 🧠 Key Points for Exams

- Always check for **empty list** (`head == null`) first.
- Handle **single node** case separately.
- Traversing till **second-last node** is crucial for safe deletion.
- After deletion, make sure the **second-last node points to NULL**.
- During insertion, don’t forget to **set new node’s next = NULL**.

---

## 💡 Visual (ASCII Diagram)

Before Insertion:  
Head → 1 → 2 → 3 → 4 → NULL

After Inserting 5:  
Head → 1 → 2 → 3 → 4 → 5 → NULL

After Deleting Last Node:  
Head → 1 → 2 → 3 → 4 → NULL