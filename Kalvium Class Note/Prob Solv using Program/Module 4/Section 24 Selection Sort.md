# 📒 Notes on Selection Sort

### **What is Selection Sort?**

- A simple sorting algorithm.
- It splits the list into:
    - **Sorted part** (grows as sorting progresses).
    - **Unsorted part** (shrinks each step).
- Process:
    
    1. Find the **smallest element** in the unsorted part.
    2. Swap it with the **first unsorted element**.
    3. Repeat until the entire list is sorted.

---

### **Algorithm Steps**

1. Start with the first index `i = 0`.
2. Find the smallest element in the range `[i … n-1]`.
3. Swap smallest with `arr[i]`.
4. Increment `i` (the sorted portion grows).
5. Repeat until `i = n-2`.

---

### **Example**

Array: `[48, 34, 12, 26]`

- Pass 1: min = 12 → swap with 48 → `[12, 34, 48, 26]`
- Pass 2: min = 26 → swap with 34 → `[12, 26, 48, 34]`
- Pass 3: min = 34 → swap with 48 → `[12, 26, 34, 48]`
- Done ✅ Sorted array: `[12, 26, 34, 48]`.

---

### **Pseudocode**

```
selectionSort(arr, n):
    for i = 0 to n-2:
        minIndex = i
        for j = i+1 to n-1:
            if arr[j] < arr[minIndex]:
                minIndex = j
        swap arr[i], arr[minIndex]

```

---

### **Complexity**

- **Time Complexity**:
    - Best: O(n²)
    - Average: O(n²)
    - Worst: O(n²)
- **Space Complexity**: O(1) (in-place sort).

---

### **Advantages**

- Easy to implement.
- Works well for small datasets.
- Fewer swaps compared to bubble sort.

### **Disadvantages**

- Very slow for large lists.
- Always O(n²), no best-case optimization.
- Not adaptive (doesn’t improve with partially sorted input).

---

# 💻 Implementations

---

### **Python**

```python
def selection_sort(arr):
    n = len(arr)
    for i in range(n - 1):
        min_idx = i
        for j in range(i + 1, n):
            if arr[j] < arr[min_idx]:
                min_idx = j
        arr[i], arr[min_idx] = arr[min_idx], arr[i]
    return arr

# Example
arr = [48, 34, 12, 26]
print("Sorted:", selection_sort(arr))

```

---

### **C++**

```cpp
#include <iostream>
#include <vector>
using namespace std;

void selectionSort(vector<int>& arr) {
    int n = arr.size();
    for (int i = 0; i < n - 1; i++) {
        int minIdx = i;
        for (int j = i + 1; j < n; j++) {
            if (arr[j] < arr[minIdx])
                minIdx = j;
        }
        swap(arr[i], arr[minIdx]);
    }
}

int main() {
    vector<int> arr = {48, 34, 12, 26};
    selectionSort(arr);
    cout << "Sorted: ";
    for (int x : arr) cout << x << " ";
    cout << endl;
    return 0;
}

```

---

### **Java**

`import java.util.Arrays;  public class SelectionSort {     public static void selectionSort(int[] arr) {         int n = arr.length;         for (int i = 0; i < n - 1; i++) {             int minIdx = i;             for (int j = i + 1; j < n; j++) {                 if (arr[j] < arr[minIdx]) {                     minIdx = j;                 }             }             int temp = arr[i];             arr[i] = arr[minIdx];             arr[minIdx] = temp;         }     }      public static void main(String[] args) {         int[] arr = {48, 34, 12, 26};         selectionSort(arr);         System.out.println("Sorted: " + Arrays.toString(arr));     } }`