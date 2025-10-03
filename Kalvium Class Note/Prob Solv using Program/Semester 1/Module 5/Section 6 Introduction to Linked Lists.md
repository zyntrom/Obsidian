# 🧠 Introduction to Linked Lists

## 🔹 Definition

A **Linked List** is a **linear data structure** where elements (called **nodes**) are linked using **pointers/references**.  
Unlike arrays, elements are **not stored in contiguous memory**.

Each node has two parts:

- **Data** → stores the actual value.
- **Pointer/Reference** → stores the address/reference of the next node.

---

### 🎯 Analogy

Think of a **treasure hunt**:

- Each **clue = a node**
- Each clue tells you **where to find the next one**
- You **can’t skip clues**; you follow one after another.

In contrast, arrays are like a **grid map** — every location (element) has a fixed address, and you can jump directly to any position.

---

## 🧩 Types of Linked Lists

1. **Singly Linked List**
    - Each node points to the **next** node.
    - The **last node** points to **null** (or `None`).
    - Traversal is **one-way**.
2. **Doubly Linked List**
    - Each node points to both **next** and **previous** nodes.
    - Allows **two-way traversal**.
3. **Circular Linked List**
    - The **last node** points to the **first node**, forming a **circle**.

🧠 _In this course, we focus only on Singly Linked Lists._

---

## ⚙️ Key Operations in Linked Lists

### 1. **Insertion**

Add a new node in:

- Beginning
- End
- Middle (after a given node)

### 2. **Deletion**

Remove a node from:

- Beginning
- End
- Specific position

### 3. **Traversal**

Visit every node **from head to end** (until pointer = `null`).

---

## 💡 Advantages Over Arrays

|Feature|Linked List|Array|
|---|---|---|
|**Size**|Dynamic (can grow/shrink)|Fixed|
|**Insertion/Deletion**|Efficient (no shifting needed)|Expensive (needs shifting)|
|**Memory Usage**|Flexible (allocates per node)|May waste unused memory|
|**Implementation**|Great for dynamic data|Better for index-based access|
```embed
title: "Introduction to Linked List"
image: "https://i.ytimg.com/vi/R9PTBwOzceo/maxresdefault.jpg"
description: "Data Structures: Introduction to Linked ListTopics discussed:1) Different ways to maintain a list in memory.2) Types of Linked List.3) Single Linked List.4) ..."
url: "https://youtu.be/R9PTBwOzceo"
favicon: ""
aspectRatio: "56.25"
```

# C++ Linked List

```embed
title: "Linked List - Implementation in C/C++"
image: "https://i.ytimg.com/vi/vcQIFT79_50/maxresdefault.jpg"
description: "See complete series on linked list here:http://www.youtube.com/watch?v=NobHlGUjV3g&list=PL2_aWCzGMAwI3W_JlcBbtYTwiQSsOTa6P&index=3In this lesson, we will see..."
url: "https://youtu.be/vcQIFT79_50"
favicon: ""
aspectRatio: "56.25"
```

# Python Linked List:

```embed
title: "Linked List - Data Structures & Algorithms Tutorials in Python #4"
image: "https://i.ytimg.com/vi/qp8u-frRAnU/maxresdefault.jpg"
description: "Linked list is a data structure similar to array in a sense that it stores bunch of items. But unlike array, linked lists are not stored in contiguous memory..."
url: "https://youtu.be/qp8u-frRAnU"
favicon: ""
aspectRatio: "56.25"
```

---

## ⚠️ Disadvantages

- **No random access** (must traverse sequentially)
- **Extra memory** for pointers
- **Slower access time** than arrays

---

## 🧱 Structure of a Node

A **Node** stores data and a reference to the next node.

### C++

```cpp
struct Node {
    int data;
    Node* next;
};

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

### Python

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

```

---

## 🚀 Universal Singly Linked List Implementation

We'll build:

1. **Node** structure
2. **LinkedList** class
3. **insert()**, **delete()**, **display()** methods

---

### Step-by-Step Logic

1. **Create Node**
    - Allocate memory.
    - Store data.
    - Set `next = null`.
2. **Insert at End**
    - If list is empty → new node becomes **head**.
    - Else → traverse till last node → set `last.next = new_node`.
3. **Delete Node by Value**
    - If list is empty → return.
    - If node to delete is **head** → move head to next.
    - Else → traverse and adjust pointers to skip the target node.
4. **Display List**
    - Start from `head`.
    - Print data of each node until `null`.

---
# Optional Code for linked list if u want:
### ✅ Code Implementation (Universal)

#### C++

```cpp
#include <iostream>
using namespace std;

struct Node {
    int data;
    Node* next;
};

class LinkedList {
    Node* head;
public:
    LinkedList() { head = nullptr; }
    void insertEnd(int val) {
        Node* newNode = new Node();
        newNode->data = val;
        newNode->next = nullptr;
        if (!head) {
            head = newNode;
            return;
        }
        Node* temp = head;
        while (temp->next) temp = temp->next;
        temp->next = newNode;
    }
    void deleteValue(int val) {
        if (!head) return;
        if (head->data == val) {
            Node* temp = head;
            head = head->next;
            delete temp;
            return;
        }
        Node* prev = nullptr;
        Node* curr = head;
        while (curr && curr->data != val) {
            prev = curr;
            curr = curr->next;
        }
        if (curr) {
            prev->next = curr->next;
            delete curr;
        }
    }
    void display() {
        Node* temp = head;
        while (temp) {
            cout << temp->data << " -> ";
            temp = temp->next;
        }
        cout << "NULL\n";
    }
};

int main() {
    LinkedList list;
    list.insertEnd(10);
    list.insertEnd(20);
    list.insertEnd(30);
    list.display();
    list.deleteValue(20);
    list.display();
}

```

---

#### Java

```java
class Node {
    int data;
    Node next;
    Node(int data) {
        this.data = data;
        this.next = null;
    }
}
class LinkedList {
    Node head;
    void insertEnd(int val) {
        Node newNode = new Node(val);
        if (head == null) {
            head = newNode;
            return;
        }
        Node temp = head;
        while (temp.next != null)
            temp = temp.next;
        temp.next = newNode;
    }
    void deleteValue(int val) {
        if (head == null) return;
        if (head.data == val) {
            head = head.next;
            return;
        }
        Node prev = null, curr = head;
        while (curr != null && curr.data != val) {
            prev = curr;
            curr = curr.next;
        }
        if (curr != null)
            prev.next = curr.next;
    }
    void display() {
        Node temp = head;
        while (temp != null) {
            System.out.print(temp.data + " -> ");
            temp = temp.next;
        }
        System.out.println("NULL");
    }
    public static void main(String[] args) {
        LinkedList list = new LinkedList();
        list.insertEnd(10);
        list.insertEnd(20);
        list.insertEnd(30);
        list.display();
        list.deleteValue(20);
        list.display();
    }
}

```

---

#### Python

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None
class LinkedList:
    def __init__(self):
        self.head = None
    def insert_end(self, val):
        new_node = Node(val)
        if not self.head:
            self.head = new_node
            return
        temp = self.head
        while temp.next:
            temp = temp.next
        temp.next = new_node
    def delete_value(self, val):
        if not self.head:
            return
        if self.head.data == val:
            self.head = self.head.next
            return
        prev = None
        curr = self.head
        while curr and curr.data != val:
            prev = curr
            curr = curr.next
        if curr:
            prev.next = curr.next
    def display(self):
        temp = self.head
        while temp:
            print(temp.data, end=" -> ")
            temp = temp.next
        print("NULL")

# Example usage
ll = LinkedList()
ll.insert_end(10)
ll.insert_end(20)
ll.insert_end(30)
ll.display()
ll.delete_value(20)
ll.display()

```

---

## 🧠 Concept Summary

|Concept|Description|
|---|---|
|**Node**|Contains `data` + `next pointer`|
|**Head**|First node in the list|
|**Traversal**|Visiting each node until `NULL`|
|**Insertion**|Add node dynamically|
|**Deletion**|Remove node and reconnect links|
|**Dynamic Size**|Grows/shrinks easily|
|**Applications**|Implement stacks, queues, graphs|