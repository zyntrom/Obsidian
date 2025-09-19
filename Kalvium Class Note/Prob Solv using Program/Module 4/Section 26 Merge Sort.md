# 📘 Notes on Merge Sort

## 🔹 What is Merge Sort?

- **Merge Sort** is a **divide-and-conquer sorting algorithm**.
- It works by **splitting the array into smaller parts**, sorting each part, and then merging them back together.
- Unlike Bubble Sort, Selection Sort, or Insertion Sort, Merge Sort has better performance on large datasets.

---

## 🔹 Steps of Merge Sort

1. **Divide**
    - Split the array into two halves until each subarray contains only **1 element**.
    - A single element is already "sorted".
2. **Conquer (Sort subarrays)**
    - Recursively apply Merge Sort on the left half and the right half.
3. **Merge**
    - Combine two sorted halves into a single sorted array.
    - This merging is done by comparing elements one by one.

---

## 🔹 Example (Array: [5, 2, 8, 1])

1. Split into two halves → [5, 2] and [8, 1]
2. Split further → [5], [2], [8], [1]
3. Merge pairs:
    - [5] + [2] → [2, 5]
    - [8] + [1] → [1, 8]
4. Merge final:
    - [2, 5] + [1, 8] → [1, 2, 5, 8]

✅ Sorted array = [1, 2, 5, 8]

---

## 🔹 Pseudocode

```
mergeSort(arr, l, r):
    if l < r:
        m = (l + r) / 2
        mergeSort(arr, l, m)
        mergeSort(arr, m+1, r)
        merge(arr, l, m, r)

merge(arr, l, m, r):
    copy left half to temp array L[]
    copy right half to temp array R[]
    merge L[] and R[] back into arr[l...r]

```
---

## 🔹 Time Complexity

- **Best Case:** O(n log n)
- **Worst Case:** O(n log n)
- **Average Case:** O(n log n)  
    👉 Always efficient compared to Bubble, Selection, and Insertion Sort (O(n²)).

---

## 🔹 Space Complexity

- **O(n)** (extra space for temporary arrays during merge).
- Not in-place (needs additional memory).

---

## 🔹 Advantages

✅ Always runs in O(n log n).  
✅ Works well for large datasets.  
✅ Stable sort (does not change the relative order of equal elements).

---

## 🔹 Disadvantages

❌ Needs extra space (O(n)).  
❌ Slower than Insertion Sort for small datasets.  
❌ Not in-place (makes temporary arrays).

---

## 🔹 Implementation Languages

- ✅ Python (simple list handling).
- ✅ C++ (arrays with temporary subarrays).
- ✅ Java (arrays with `copyOfRange` or loops).

```embed
title: "CS50 Shorts - Merge Sort"
image: ""
description: "Enjoy the videos and music you love, upload original content, and share it all with friends, family, and the world on YouTube."
url: "https://youtu.be/Pr2Jf83_kG0"
favicon: ""
```

```embed
title: "Merge sort in 3 minutes"
image: ""
description: "Step by step instructions showing how to run merge sort.Code: https://github.com/msambol/dsa/blob/master/sort/merge_sort.py (different than video, I added th..."
url: "https://youtu.be/4VqmGXwpLqc"
favicon: ""
```

## 🐍 Python (simple arrays/lists)

```python
def merge_sort(arr):
    if len(arr) <= 1:
        return arr
    
    mid = len(arr) // 2
    left = merge_sort(arr[:mid])
    right = merge_sort(arr[mid:])
    
    return merge(left, right)

def merge(left, right):
    result = []
    i = j = 0
    
    while i < len(left) and j < len(right):
        if left[i] < right[j]:
            result.append(left[i])
            i += 1
        else:
            result.append(right[j])
            j += 1
    
    result.extend(left[i:])
    result.extend(right[j:])
    return result

# Example
arr = [5, 2, 8, 1]
print("Sorted:", merge_sort(arr))

```

---

## 💻 C++ (without `vector`, using plain arrays)

```cpp
#include <iostream>
using namespace std;

void merge(int arr[], int l, int m, int r) {
    int n1 = m - l + 1;
    int n2 = r - m;
    int L[1000], R[1000];  // temporary arrays
    for (int i = 0; i < n1; i++) L[i] = arr[l + i];
    for (int j = 0; j < n2; j++) R[j] = arr[m + 1 + j];

    int i = 0, j = 0, k = l;
    while (i < n1 && j < n2) {
        if (L[i] <= R[j]) arr[k++] = L[i++];
        else arr[k++] = R[j++];
    }
    while (i < n1) arr[k++] = L[i++];
    while (j < n2) arr[k++] = R[j++];
}

void mergeSort(int arr[], int l, int r) {
    if (l < r) {
        int m = (l + r) / 2;
        mergeSort(arr, l, m);
        mergeSort(arr, m + 1, r);
        merge(arr, l, m, r);
    }
}

int main() {
    int arr[] = {5, 2, 8, 1};
    int n = sizeof(arr) / sizeof(arr[0]);

    mergeSort(arr, 0, n - 1);

    cout << "Sorted: ";
    for (int i = 0; i < n; i++) cout << arr[i] << " ";
    cout << endl;
}

```

---

## ☕ Java (arrays, no extra libraries)

```java
import java.util.*;

public class MergeSortSimple {
    public static void merge(int arr[], int l, int m, int r) {
        int n1 = m - l + 1;
        int n2 = r - m;
        int L[] = new int[n1];
        int R[] = new int[n2];
        for (int i = 0; i < n1; i++) L[i] = arr[l + i];
        for (int j = 0; j < n2; j++) R[j] = arr[m + 1 + j];
        int i = 0, j = 0, k = l;
        while (i < n1 && j < n2) {
            if (L[i] <= R[j]) arr[k++] = L[i++];
            else arr[k++] = R[j++];
        }
        while (i < n1) arr[k++] = L[i++];
        while (j < n2) arr[k++] = R[j++];
    }
    public static void mergeSort(int arr[], int l, int r) {
        if (l < r) {
            int m = (l + r) / 2;
            mergeSort(arr, l, m);
            mergeSort(arr, m + 1, r);
            merge(arr, l, m, r);
        }
    }
    public static void main(String[] args) {
        int arr[] = {5, 2, 8, 1};
        mergeSort(arr, 0, arr.length - 1);
        System.out.println("Sorted: " + Arrays.toString(arr));
    }
}

```