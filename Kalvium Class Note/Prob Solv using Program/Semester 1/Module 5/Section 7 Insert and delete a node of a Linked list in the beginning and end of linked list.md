# 🧠 Insert and Delete a Node at Beginning and End in Linked List

## 📘 Concept Recap

A **Linked List** is a dynamic linear data structure made up of **nodes**.  
Each **node** contains:

- **Data** → stores the actual value.
- **Next pointer/reference** → points to the next node.

---

## 🧱 Node Structure

### C++

```cpp
struct Node {
   int data;
   struct Node* next;
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

## ⚙️ Core Operations

We'll perform:

1. **Insertion at Beginning**
2. **Deletion at Beginning**
3. **Insertion at End**
4. **Deletion at End**
5. **Display (Traversal)**

---

## 🧩 1. Insertion at Beginning

### 🧠 Logic:

- Create a **new node**.
- Point its `next` to **current head**.
- Make this **new node** the new head.

### C++

```cpp
void insertAtBeginning(int new_data) {
    Node* new_node = new Node();
    new_node->data = new_data;
    new_node->next = head;   // new node points to old head
    head = new_node;         // new node becomes head
}

```

### Python

```python
def insert_at_beginning(self, data):
    new_node = Node(data)
    new_node.next = self.head
    self.head = new_node

```

### Java

```java
void insertAtBeginning(int data) {
    Node newNode = new Node(data);
    newNode.next = head;
    head = newNode;
}

```
---

## 🧩 2. Deletion at Beginning

### 🧠 Logic:

- If list is empty → return.
- Set `new_head` to `head.next`.
- Delete old head.
- Update head to new_head.

### C++

```cpp
Node* deleteAtBeginning(Node* head) {
    if (head == nullptr) return nullptr;
    Node* new_head = head->next;
    delete head;
    return new_head;
}

```

### Python

```python
def delete_at_beginning(self):
    if self.head is None:
        return
    new_head = self.head.next
    del self.head
    self.head = new_head

```
### Java

```java
void deleteAtBeginning() {
    if (head == null) return;
    head = head.next;  // old head removed automatically by GC
}

```

---

## 🧩 3. Insertion at End

### 🧠 Logic:

- Create a **new node**.
- If list is empty → it becomes head.
- Else → traverse to last node → link last node’s `next` to new node.

### C++

```cpp
void insertAtEnd(int data) {
    Node* new_node = new Node();
    new_node->data = data;
    new_node->next = nullptr;

    if (head == nullptr) {
        head = new_node;
        return;
    }

    Node* temp = head;
    while (temp->next != nullptr)
        temp = temp->next;

    temp->next = new_node;
}

```

### Python

```python
def insert_at_end(self, data):
    new_node = Node(data)
    if self.head is None:
        self.head = new_node
        return
    temp = self.head
    while temp.next:
        temp = temp.next
    temp.next = new_node

```

### Java

`void insertAtEnd(int data) {     Node newNode = new Node(data);     if (head == null) {         head = newNode;         return;     }     Node temp = head;     while (temp.next != null)         temp = temp.next;     temp.next = newNode; }`

---

## 🧩 4. Deletion at End

### 🧠 Logic:

- If list empty → return.
    
- If only one node → make head = null.
    
- Else → traverse to second-last node → set its `next = null`.
    

### C++

`void deleteAtEnd() {     if (head == nullptr) return;      if (head->next == nullptr) {         delete head;         head = nullptr;         return;     }      Node* temp = head;     while (temp->next->next != nullptr)         temp = temp->next;      delete temp->next;     temp->next = nullptr; }`

### Python

`def delete_at_end(self):     if self.head is None:         return     if self.head.next is None:         self.head = None         return     temp = self.head     while temp.next.next:         temp = temp.next     temp.next = None`

### Java

`void deleteAtEnd() {     if (head == null) return;     if (head.next == null) {         head = null;         return;     }     Node temp = head;     while (temp.next.next != null)         temp = temp.next;     temp.next = null; }`

---

## 🧩 5. Display (Traversal)

### 🧠 Logic:

- Start from head.
    
- Print each node’s data.
    
- Move to next node until null.
    

### C++

`void display() {     Node* current = head;     while (current != nullptr) {         cout << current->data << " ";         current = current->next;     }     cout << endl; }`

### Python

`def display(self):     current = self.head     while current:         print(current.data, end=" ")         current = current.next     print()`

### Java

`void display() {     Node temp = head;     while (temp != null) {         System.out.print(temp.data + " ");         temp = temp.next;     }     System.out.println(); }`

---

## 🧠 Example Walkthrough

### Input:

`6 10 20 30 40 50 60`

### Step-by-Step Process:

1. **Insert at Beginning** in order:
    
    - Start: NULL
        
    - Insert 10 → [10]
        
    - Insert 20 → [20 → 10]
        
    - Insert 30 → [30 → 20 → 10]
        
    - Insert 40 → [40 → 30 → 20 → 10]
        
    - Insert 50 → [50 → 40 → 30 → 20 → 10]
        
    - Insert 60 → [60 → 50 → 40 → 30 → 20 → 10]
        
2. **Delete at Beginning** once:
    
    - Remove 60 → [50 → 40 → 30 → 20 → 10]
        

### Output:

`50 40 30 20 10`

---

## 🧮 Dry Run Example

|Step|Operation|Linked List|
|---|---|---|
|1|Insert 10|10|
|2|Insert 20|20 → 10|
|3|Insert 30|30 → 20 → 10|
|4|Delete Beginning|20 → 10|
|5|Insert End (40)|20 → 10 → 40|
|6|Delete End|20 → 10|

---

## 🧠 Concept Summary

|Operation|Description|
|---|---|
|**Insert at Beginning**|Add node before head|
|**Delete at Beginning**|Remove head node|
|**Insert at End**|Add node after last node|
|**Delete at End**|Remove last node|
|**Display**|Traverse and print all nodes|