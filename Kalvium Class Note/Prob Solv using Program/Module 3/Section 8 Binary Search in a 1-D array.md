# 📝 Notes: Binary Search in a 1-D Array

## 📌 Problem Statement

Write a program to implement **Binary Search**.  
The program should search for a target element in a sorted array and return the index (position) if found, otherwise return `-1`.

---

## ⚙️ Approach (Divide & Conquer)

1. Start with two pointers:
    - `low = 0` (first index)
    - `high = n-1` (last index).
2. Find the middle index: `mid = (low + high) / 2`.
3. Compare `arr[mid]` with target:
    
    - If `arr[mid] == target` → found! Return `mid`.
    - If `arr[mid] < target` → search **right half** (`low = mid + 1`).
    - If `arr[mid] > target` → search **left half** (`high = mid - 1`).
4. Repeat until `low > high`.
5. If not found, return `-1`.

---

## ✅ Example

**Input**

```
Array: 11 14 26 28 33 49 Target: 28
```

**Steps**

- `low = 0, high = 5 → mid = 2 → arr[2] = 26` (target > 26 → search right half).
- `low = 3, high = 5 → mid = 4 → arr[4] = 33` (target < 33 → search left half).
- `low = 3, high = 3 → mid = 3 → arr[3] = 28` (FOUND at index 3).

**Output**

```
3
```

---

## 💻 Code Implementations

### 🔹 cpp Code

```cpp
#include <iostream>
using namespace std;

int binarySearch(int arr[], int n, int target) {
    int low = 0, high = n - 1;
    while (low <= high) {
        int mid = (low + high) / 2;
        if (arr[mid] == target) {
            return mid; // Found target
        } else if (arr[mid] < target) {
            low = mid + 1; // Search right half
        } else {
            high = mid - 1; // Search left half
        }
    }
    return -1; // Not found
}

int main() {
    int n;
    cin >> n;
    int arr[n];
    // Input array
    for (int i = 0; i < n; i++) {
        cin >> arr[i];
    }
    int target;
    cin >> target;
    int result = binarySearch(arr, n, target);
    cout << result << endl;
    return 0;
}

```

---

### 🔹 Python Code

```python
def binary_search(arr, target):
    low = 0
    high = len(arr) - 1
    while low <= high:
        mid = (low + high) // 2  # middle index
        if arr[mid] == target:
            return mid  # found
        elif arr[mid] < target:
            low = mid + 1  # move right
        else:
            high = mid - 1  # move left
    return -1  # not found

# Input
n = int(input())
arr = list(map(int, input().split()))
target = int(input())

result = binary_search(arr, target)
print(result)

```

---

### 🔹 Java Code

```java
import java.util.Scanner;

public class BinarySearch {
    public static int binarySearch(int[] arr, int target) {
        int low = 0;
        int high = arr.length - 1;
        while (low <= high) {
            int mid = (low + high) / 2;
            if (arr[mid] == target) {
                return mid; // found
            } else if (arr[mid] < target) {
                low = mid + 1; // search right
            } else {
                high = mid - 1; // search left
            }
        }
        return -1; // not found
    }
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[] arr = new int[n];
        // Input array
        for (int i = 0; i < n; i++) {
            arr[i] = sc.nextInt();
        }
        int target = sc.nextInt();
        int result = binarySearch(arr, target);
        System.out.println(result);
        sc.close();
    }
}

```

---

```embed
title: "Binary search in 4 minutes"
image: "https://i.ytimg.com/vi/fDKIpRe8GW4/maxresdefault.jpg"
description: "Binary search in 4 minutes.Code: https://github.com/msambol/dsa/blob/master/search/binary_search.pySources:1. Introduction To Algorithms, Third Edition (CLRS..."
url: "https://youtu.be/fDKIpRe8GW4"
favicon: ""
aspectRatio: "56.25"
```

## 🎯 Key Points

- Binary Search only works on **sorted arrays**.
- Much faster than Linear Search.
- **Time Complexity:**
    - Worst case: **O(log n)**
    - Best case: **O(1)** (if found at first mid).
- Useful when you have **large datasets** and need frequent searches.