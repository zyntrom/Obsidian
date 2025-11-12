# 📒 5.28 Fast and Slow Pointer Technique

---

## 🔹 Problem Statement

**Task:** Find the **middle element** of an array using the **fast and slow pointer technique**.

- The **fast pointer** moves **two steps at a time**
- The **slow pointer** moves **one step at a time**
- When the fast pointer reaches the end, the slow pointer will be at the **middle element**
- For **even-length arrays**, return the **left middle element**

---

## 🔹 Example

**Example 1:**

```
Input: 5 1 2 3 4 5  Output: 3
```

- Fast moves: 1 → 3 → 5
- Slow moves: 1 → 2 → 3 → middle is 3

**Example 2:**

```
Input: 6 10 20 30 40 50 60  Output: 30
```

- Fast moves: 10 → 30 → 50 → end
- Slow moves: 10 → 20 → 30 → middle is 30

---

## 🔹 Approach

1. **Initialize Pointers:**
    - `slow = 0`, `fast = 0`
2. **Traverse Array:**
    - While `fast` is within bounds (`fast < N`) and `fast + 1 < N`:
        - Move `fast` **two steps forward**
        - Move `slow` **one step forward**
3. **Return Middle Element:**
    - The element at `arr[slow]` is the middle

---

## 🔹 Python Implementation

```python
n = int(input())
arr = list(map(int, input().split()))

slow = 0
fast = 0

while fast < n - 1:
    slow += 1
    fast += 2

print(arr[slow])

```

---

## 🔹 C++ Implementation

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    int n;
    cin >> n;
    vector<int> arr(n);
    for(int i=0; i<n; i++) cin >> arr[i];

    int slow = 0, fast = 0;
    while(fast < n - 1){
        slow++;
        fast += 2;
    }

    cout << arr[slow] << endl;
    return 0;
}

```

---

## 🔹 Java Implementation

```java
import java.util.*;

public class MiddleElement {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[] arr = new int[n];
        for(int i=0;i<n;i++) arr[i]=sc.nextInt();
        int slow = 0, fast = 0;
        while(fast < n - 1){
            slow++;
            fast += 2;
        }
        System.out.println(arr[slow]);
    }
}

```

---

## 🔹 Complexity Analysis

- **Time Complexity:** O(N/2) → simplified to **O(N)**
- **Space Complexity:** O(1) → only two pointers are used

---

## 🔹 Key Takeaways

- The fast pointer moving **twice as fast** ensures slow reaches the **middle efficiently**
- Works for both **odd** and **even** length arrays
- Can be applied in **linked lists** to find middle nodes, detect cycles, etc.