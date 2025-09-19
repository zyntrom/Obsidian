# 📘 Notes on Quick Sort

## 🔹 What is Quick Sort?

- **Quick Sort** is a **divide-and-conquer algorithm**.
- It picks a **pivot element**, then partitions the array so that:
    - Elements smaller than the pivot go to the **left**.
    - Elements larger than the pivot go to the **right**.
- The pivot is placed in its **correct sorted position**.
- Recursively apply the same process to the left and right subarrays.

---

## 🔹 Steps of Quick Sort

1. **Choose a Pivot**
    - Common strategies: first element, last element, middle element, or a random element.
2. **Partition**
    - Rearrange the array so that elements less than pivot are on the left, greater ones on the right.
3. **Recursive Sort**
    - Apply quick sort on the left and right subarrays.
4. **Combine**
    - Once subarrays are sorted, the full array is sorted (no extra merge step needed).

---

## 🔹 Example (Array: [78, 47, 58, 95, 76, 94])

1. Choose pivot = 94.
    - Partition → [78, 47, 58, 76] | 94 | [95]
2. Apply Quick Sort on left subarray [78, 47, 58, 76].
    - Suppose pivot = 76 → [47, 58] | 76 | [78]
3. Apply Quick Sort on [47, 58].
    - Pivot = 58 → [47] | 58
4. Combine → [47, 58, 76, 78] | 94 | [95]

✅ Final Sorted Array = [47, 58, 76, 78, 94, 95]

---

## 🔹 Pseudocode

```
quickSort(arr, low, high):
    if low < high:
        pi = partition(arr, low, high)
        quickSort(arr, low, pi - 1)
        quickSort(arr, pi + 1, high)

partition(arr, low, high):
    pivot = arr[high]
    i = low - 1
    for j = low to high - 1:
        if arr[j] <= pivot:
            i++
            swap arr[i], arr[j]
    swap arr[i+1], arr[high]
    return i+1

```

---

## 🔹 Time Complexity

- **Best Case:** O(n log n) (when pivot splits array evenly).
- **Worst Case:** O(n²) (when pivot always splits badly, e.g., already sorted input with poor pivot choice).
- **Average Case:** O(n log n).

👉 Faster than Merge Sort in practice (less memory usage).

---

## 🔹 Space Complexity

- **Best/Average Case:** O(log n) (recursive stack).
- **Worst Case:** O(n) (highly unbalanced partitions).

---

## 🔹 Advantages

✅ Faster than Bubble, Selection, and Insertion sort.  
✅ In-place sorting (no extra arrays like Merge Sort).  
✅ Very efficient for large datasets.

---

## 🔹 Disadvantages

❌ Worst-case O(n²) if pivot choice is poor.  
❌ Not stable (may change relative order of equal elements).  
❌ Recursive calls may cause stack overflow for very large arrays.

## 🐍 Python (Quick Sort)

```python
def partition(arr, low, high):
    pivot = arr[high]   # choose last element as pivot
    i = low - 1
    for j in range(low, high):
        if arr[j] <= pivot:
            i += 1
            arr[i], arr[j] = arr[j], arr[i]
    arr[i+1], arr[high] = arr[high], arr[i+1]
    return i + 1

def quick_sort(arr, low, high):
    if low < high:
        pi = partition(arr, low, high)
        quick_sort(arr, low, pi - 1)
        quick_sort(arr, pi + 1, high)

# Example
arr = [78, 47, 58, 95, 76, 94]
quick_sort(arr, 0, len(arr) - 1)
print("Sorted:", arr)

```

---

## 💻 C++ (Quick Sort with plain arrays)

```cpp
#include <iostream>
using namespace std;

int partition(int arr[], int low, int high) {
    int pivot = arr[high]; // pivot is last element
    int i = low - 1;
    for (int j = low; j < high; j++) {
        if (arr[j] <= pivot) {
            i++;
            swap(arr[i], arr[j]);
        }
    }
    swap(arr[i + 1], arr[high]);
    return i + 1;
}

void quickSort(int arr[], int low, int high) {
    if (low < high) {
        int pi = partition(arr, low, high);
        quickSort(arr, low, pi - 1);
        quickSort(arr, pi + 1, high);
    }
}

int main() {
    int arr[] = {78, 47, 58, 95, 76, 94};
    int n = sizeof(arr) / sizeof(arr[0]);

    quickSort(arr, 0, n - 1);

    cout << "Sorted: ";
    for (int i = 0; i < n; i++) cout << arr[i] << " ";
    cout << endl;
}

```

---

## ☕ Java (Quick Sort)

```java
import java.util.*;

public class QuickSortSimple {
    public static int partition(int arr[], int low, int high) {
        int pivot = arr[high];  // last element as pivot
        int i = low - 1;
        for (int j = low; j < high; j++) {
            if (arr[j] <= pivot) {
                i++;
                int temp = arr[i];
                arr[i] = arr[j];
                arr[j] = temp;
            }
        }
        int temp = arr[i + 1];
        arr[i + 1] = arr[high];
        arr[high] = temp;
        return i + 1;
    }
    public static void quickSort(int arr[], int low, int high) {
        if (low < high) {
            int pi = partition(arr, low, high);
            quickSort(arr, low, pi - 1);
            quickSort(arr, pi + 1, high);
        }
    }
    public static void main(String[] args) {
        int arr[] = {78, 47, 58, 95, 76, 94};
        quickSort(arr, 0, arr.length - 1);
        System.out.println("Sorted: " + Arrays.toString(arr));
    }
}

```