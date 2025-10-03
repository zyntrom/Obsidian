# 📒 Notes: Introduction to Stacks & Queues

---

## 🔹 Stacks

**Definition:**

- A **stack** is a linear data structure that follows **Last In, First Out (LIFO)**.
- The **last element added** is the **first element removed**.
- Real-life analogy: A stack of plates.

### Key Operations:

|Operation|Description|
|---|---|
|**Push**|Add an element to the top of the stack|
|**Pop**|Remove the top element|
|**Peek/Top**|View the top element without removing|
|**isEmpty**|Check if the stack is empty|

### Common Uses:

- Undo mechanisms in editors
- Function call management (call stack)
- Expression evaluation (infix → postfix)

---

### 🔹 Stack Implementations

#### Python

```python
stack = []

# Push
stack.append(10)

# Pop
top = stack.pop()

# Peek/Top
top = stack[-1] if stack else None

# isEmpty
empty = len(stack) == 0

```

#### Java

```java
import java.util.Stack;

Stack<Integer> stack = new Stack<>();

// Push
stack.push(10);

// Pop
int top = stack.pop();

// Peek/Top
int peek = stack.peek();

// isEmpty
boolean empty = stack.isEmpty();

```

#### C++

```cpp
#include <stack>
#include <iostream>
using namespace std;

stack<int> s;

// Push
s.push(10);

// Pop
int top = s.top();
s.pop();

// Peek/Top
int peek = s.top();

// isEmpty
bool empty = s.empty();

```

---

## 🔹 Queues

**Definition:**

- A **queue** is a linear data structure that follows **First In, First Out (FIFO)**.
- The **first element added** is the **first element removed**.
- Real-life analogy: People waiting in line at a checkout.

### Key Operations:

|Operation|Description|
|---|---|
|**Enqueue**|Add an element to the end of the queue|
|**Dequeue**|Remove element from the front|
|**Front/Peek**|View the front element without removing|
|**isEmpty**|Check if the queue is empty|

### Common Uses:

- Task scheduling
- Web server request handling
- Resource management in simulations

---

### 🔹 Queue Implementations

#### Python

```python
from collections import deque

queue = deque()

# Enqueue
queue.append(10)

# Dequeue
front = queue.popleft()

# Front/Peek
front = queue[0] if queue else None

# isEmpty
empty = len(queue) == 0

```

#### Java

```java
import java.util.LinkedList;
import java.util.Queue;

Queue<Integer> queue = new LinkedList<>();

// Enqueue
queue.add(10);

// Dequeue
int front = queue.poll();

// Front/Peek
int peek = queue.peek();

// isEmpty
boolean empty = queue.isEmpty();

```

#### C++

```cpp
#include <queue>
#include <iostream>
using namespace std;

queue<int> q;

// Enqueue
q.push(10);

// Dequeue
int front = q.front();
q.pop();

// Front/Peek
int peek = q.front();

// isEmpty
bool empty = q.empty();

```

---

## 🔹 Key Takeaways

- **Stacks** → LIFO → useful for function calls, undo, expression evaluation.
- **Queues** → FIFO → useful for scheduling, request handling, simulations.
- Python’s `list` can act as a stack; `deque` is preferred for queues.
- Java provides `Stack` and `Queue` (`LinkedList` or `PriorityQueue`) implementations.
- C++ STL provides `stack` and `queue` containers for easy usage.