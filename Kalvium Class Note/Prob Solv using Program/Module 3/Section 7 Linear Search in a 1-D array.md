# 📝 Notes: Linear Search in a 1-D Array

## 📌 Problem Statement

Write a program to implement **Linear Search**.  
The program should search for a given target element inside an array and return the index (position) if found, otherwise return `-1`.

---

## ⚙️ Approach

1. Start from the **first element** of the array.
2. Compare each element with the target.
3. If the element matches the target → return its index.
4. If no element matches after checking all → return `-1`.

This is also called **Sequential Search** since we go one-by-one.

---

## ✅ Example

**Input**

`Array: 10 5 8 2 15 Target: 8`

**Step-by-Step Search**

- Compare 10 with 8 → Not equal.
- Compare 5 with 8 → Not equal.
- Compare 8 with 8 → Found at index 2.

**Output**

`Element found at index 2`

If the target was `12`, it would not be found, so output would be `-1`.

---

## 💻 Code Implementations

### 🔹 C++ Code

```c++
#include <iostream>
using namespace std;

int linearSearch(int arr[], int n, int target) {
    for (int i = 0; i < n; i++) {
        if (arr[i] == target) {
            return i; // return index if found
        }
    }
    return -1; // not found
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
    
    int result = linearSearch(arr, n, target);
    cout << result << endl;
    
    return 0;
}

```

---

### 🔹 Python Code

```python
def linear_search(arr, target):
    for i in range(len(arr)):
        if arr[i] == target:
            return i  # return index if found
    return -1  # not found

# Input
n = int(input())
arr = list(map(int, input().split()))
target = int(input())

# Call function
result = linear_search(arr, target)
print(result)

```

---

### 🔹 Java Code

```java
import java.util.Scanner;

public class LinearSearch {
    public static int linearSearch(int[] arr, int target) {
        for (int i = 0; i < arr.length; i++) {
            if (arr[i] == target) {
                return i; // return index if found
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
        
        int result = linearSearch(arr, target);
        System.out.println(result);
        
        sc.close();
    }
}

```

---

## 🎯 Key Points

- Linear Search checks **every element one-by-one**.
- Time Complexity: **O(n)** (worst case, check all).
- Works on **unsorted arrays**.
- Simple, but inefficient for large datasets.