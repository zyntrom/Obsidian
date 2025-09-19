# 📒 Notes on Bubble Sort

### **What is Bubble Sort?**

- Also called the **sinking sort**.
- Works by **repeatedly swapping adjacent elements** if they are in the wrong order.
- Larger elements “bubble up” to the end of the list in each pass.
- After each pass, the next largest element is placed in its correct position.

---

### **Algorithm Steps**

1. Start from the beginning of the array.
2. Compare adjacent elements:
    - If `arr[j] > arr[j+1]`, swap them.
3. After the first pass, the **largest element** moves to the last position.
4. Repeat the process for the remaining unsorted portion.
5. Continue until no swaps are needed (array is sorted).

---

### **Example**

Array: `[6, 3, 0, 5, 1]`

- **Pass 1**: `[3, 0, 5, 1, 6]` (6 bubbled to end).
- **Pass 2**: `[0, 3, 1, 5, 6]`.
- **Pass 3**: `[0, 1, 3, 5, 6]`.
- **Pass 4**: Already sorted, stops.

✅ Sorted array = `[0, 1, 3, 5, 6]`.

---

### **Pseudocode**

```
bubbleSort(arr, n):     
	for i = 0 to n-2:         
		swapped = false         
		for j = 0 to n-i-2:             
			if arr[j] > arr[j+1]:                 
				swap(arr[j], arr[j+1])                 
		swapped = true         
		if not swapped:             
			break
```

---

### **Complexity**

- **Time Complexity**:
    - Best: O(n) (already sorted, with optimization).
    - Average: O(n²).
    - Worst: O(n²) (reverse order).
- **Space Complexity**: O(1) (in-place sort).

---

### **Advantages**

- Very simple to understand and implement.
- Works well for **small datasets**.
- With optimization (swap flag), it can stop early if array is already sorted.

### **Disadvantages**

- Very inefficient for large arrays.
- Always quadratic (O(n²)) in average/worst case.
- Performs too many swaps compared to other sorting algorithms.

---

# 💻 Implementations

---

### **Python**

```python
def bubble_sort(arr):
    n = len(arr)
    for i in range(n - 1):
        swapped = False
        for j in range(n - i - 1):
            if arr[j] > arr[j + 1]:
                arr[j], arr[j + 1] = arr[j + 1], arr[j]
                swapped = True
        if not swapped:
            break
    return arr
# Example
arr = [6, 3, 0, 5, 1]
print("Sorted:", bubble_sort(arr))

```

---

### **C++**

```cpp
#include <iostream>
using namespace std;

void bubbleSort(int arr[], int n) {
    for (int i = 0; i < n - 1; i++) {
        bool swapped = false;
        for (int j = 0; j < n - i - 1; j++) {
            if (arr[j] > arr[j + 1]) {
                swap(arr[j], arr[j + 1]);
                swapped = true;
            }
        }
        if (!swapped) break; // optimization: stop if already sorted
    }
}

int main() {
    int arr[] = {6, 3, 0, 5, 1};
    int n = sizeof(arr) / sizeof(arr[0]);
    bubbleSort(arr, n);
    cout << "Sorted: ";
    for (int i = 0; i < n; i++) {
        cout << arr[i] << " ";
    }
    cout << endl;
    return 0;
}

```

---

### **Java**

```java
import java.util.Arrays;

public class BubbleSort {
    public static void bubbleSort(int[] arr) {
        int n = arr.length;
        for (int i = 0; i < n - 1; i++) {
            boolean swapped = false;
            for (int j = 0; j < n - i - 1; j++) {
                if (arr[j] > arr[j + 1]) {
                    int temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                    swapped = true;
                }
            }
            if (!swapped) break;
        }
    }
    public static void main(String[] args) {
        int[] arr = {6, 3, 0, 5, 1};
        bubbleSort(arr);
        System.out.println("Sorted: " + Arrays.toString(arr));
    }
}
```

---

✅ Now you have:

- **Notes** (definition, steps, example, pros & cons).
- **Pseudocode**.
- **Implementations in Python, C++, Java**.