# 📒 5.26 Implementing Sliding Window Technique

---

## 🔹 Problem Statement

Given:

- An array `arr[]` of size `N`
- An integer `K` representing the subarray size

Task: Calculate the **sum of all subarrays of size K** using the **sliding window technique**.

**Goal:** Avoid recalculating sums from scratch for every subarray.

---

## 🔹 Approach (Sliding Window Technique)

1. **Initialize the window:**
    - Calculate the sum of the **first K elements** → this is the first window sum.
2. **Slide the window:**
    - Iterate from index `K` to `N-1`.
    - Update the sum by **subtracting the element leaving the window** (`arr[i-K]`) and **adding the new element entering** (`arr[i]`).
3. **Print/Store the sum:**
    - Print each updated sum as the window slides.

---

## 🔹 Dry Run Example

**Input:**

```
arr = [1, 2, 3, 4, 5, 6], K = 3
```

**Step 1: Initial Window:**

- Sum of first 3 elements → 1 + 2 + 3 = 6

**Step 2: Slide Window:**

- Next window: remove 1, add 4 → 2 + 3 + 4 = 9
- Next window: remove 2, add 5 → 3 + 4 + 5 = 12
- Next window: remove 3, add 6 → 4 + 5 + 6 = 15

**Output:**

`6 9 12 15`

---

## 🔹 Pseudo Code

```
function slidingWindowSum(arr, N, K):
    windowSum = sum of first K elements
    print windowSum

    for i = K to N-1:
        windowSum = windowSum - arr[i-K] + arr[i]
        print windowSum

```

---

## 🔹 Python Implementation

```python
N, K = map(int, input().split())
arr = list(map(int, input().split()))

# Initial window sum
window_sum = sum(arr[:K])
print(window_sum, end=' ')

# Slide the window
for i in range(K, N):
    window_sum = window_sum - arr[i-K] + arr[i]
    print(window_sum, end=' ')

```

---

## 🔹 C++ Implementation

```cpp
#include <iostream>
#include <vector>
using namespace std;

int main() {
    int N, K;
    cin >> N >> K;
    vector<long long> arr(N);
    for(int i=0; i<N; i++) cin >> arr[i];

    long long windowSum = 0;
    for(int i=0; i<K; i++) windowSum += arr[i];
    cout << windowSum << " ";

    for(int i=K; i<N; i++) {
        windowSum = windowSum - arr[i-K] + arr[i];
        cout << windowSum << " ";
    }
    return 0;
}

```

---

## 🔹 Java Implementation

```java
import java.util.Scanner;

public class SlidingWindow {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int N = sc.nextInt();
        int K = sc.nextInt();
        long[] arr = new long[N];
        for(int i=0; i<N; i++) arr[i] = sc.nextLong();

        long windowSum = 0;
        for(int i=0; i<K; i++) windowSum += arr[i];
        System.out.print(windowSum + " ");

        for(int i=K; i<N; i++) {
            windowSum = windowSum - arr[i-K] + arr[i];
            System.out.print(windowSum + " ");
        }
    }
}

```

---

## 🔹 Complexity Analysis

- **Time Complexity:** O(N) → each element is processed once
    
- **Space Complexity:** O(1) → only a few variables are used, no extra array needed
    

---

## 🔹 Key Takeaways

- Sliding window reduces **redundant calculations**
    
- Works best for problems involving **consecutive subarrays or substrings**
    
- Can be adapted for **maximum, minimum, sum, average, or other computations** over a window