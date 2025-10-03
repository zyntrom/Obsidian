# 📒 Notes: Queue Implementation Using Arrays

---

## 🔹 Problem Statement

Implement a **queue** using an **array** that supports the following operations:

1. **Enqueue** → Add an element to the **rear** of the queue
2. **Dequeue** → Remove and return the element at the **front**
3. **Peek/Front** → Return the element at the **front** without removing it

**Input:**

- First line: `N` → number of elements to enqueue
- Second line: `N` space-separated integers → elements to enqueue

**Output:**

- Each element dequeued printed **in order**, each on a new line

---

## 🔹 Example

### Example 1

**Input:**

```
5 1 2 3 4 5
```

**Output:**

```
1 2 3 4 5
```

### Example 2

**Input:**

```
3 10 20 30
```

**Output:**
```
10 20 30
```

### Example 3

**Input:**

```
4 -5 0 5 -10
```

**Output:**

```
-5 0 5 -10
```

---

## 🔹 Approach (Array-based Queue)

1. **Initialize:**
    - Array (or list) of size `N`
    - Two pointers:
        - `front = -1` → first element index
        - `rear = -1` → last element index
2. **Enqueue:**
    - If first element → set `front = 0`
    - Increment `rear` and insert element at `rear`
3. **Dequeue:**
    - Print element at `front`
    - Increment `front`
    - Stop when `front > rear` → queue empty
4. **Peek (Optional):**
    - Return element at `front` without removing

**Time Complexity:**
- `O(1)` per enqueue/dequeue

**Space Complexity:**

- `O(N)`

```embed
title: "Queue Data Structure implementation using Array - C++"
image: "https://i.ytimg.com/vi/jZ7Sds6ttZs/maxresdefault.jpg"
description: "To implement queue data structure using array and create a program/code in C++ to understand how we can implement the logic in our code and create a queue us..."
url: "https://youtu.be/jZ7Sds6ttZs"
favicon: ""
aspectRatio: "56.25"
```

---

## 🔹 Code Implementations

### ✅ Python Implementation

```python
N = int(input())
arr = list(map(int, input().split()))
front = 0
rear = N - 1

# Dequeue all elements
while front <= rear:
    print(arr[front])
    front += 1

```

---

### ✅ Java Implementation

```java
import java.util.Scanner;

public class QueueArray {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int N = sc.nextInt();
        int[] queue = new int[N];
        for (int i = 0; i < N; i++) {
            queue[i] = sc.nextInt();
        }
        int front = 0;
        int rear = N - 1;

        while (front <= rear) {
            System.out.println(queue[front]);
            front++;
        }
    }
}

```

---

### ✅ C++ Implementation

```cpp
#include <iostream>
using namespace std;

int main() {
    int N;
    cin >> N;
    int* queue = new int[N];
    for (int i = 0; i < N; i++) cin >> queue[i];

    int front = 0, rear = N - 1;
    while (front <= rear) {
        cout << queue[front] << endl;
        front++;
    }

    delete[] queue;
    return 0;
}

```

---

## 🔹 Key Takeaways

- Simple **array-based queue** using **two pointers**: `front` and `rear`
- **Enqueue:** insert at rear
- **Dequeue:** remove from front
- **Stop Condition:** `front > rear` → queue empty
- **Time Complexity:** `O(1)` per operation
- **Space Complexity:** `O(N)`