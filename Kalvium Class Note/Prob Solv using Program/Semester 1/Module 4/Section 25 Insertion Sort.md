# 📒 Notes on Insertion Sort

### **What is Insertion Sort?**

- A simple sorting algorithm.
- Works like **arranging playing cards in your hand**.
- Builds a **sorted subarray** one element at a time by inserting each new element into its correct position.

---

### **Algorithm Steps**

1. Consider the **first element** as already sorted.
2. Pick the **next element** → call it **key**.
3. Compare the key with the elements in the sorted portion (to its left).
    - Shift all larger elements one step to the right.
4. Insert the key in its correct place.
5. Repeat until all elements are placed.

---

### **Example Walkthrough**

Array: `[84, 43, 21, 62]`

- **Pass 1**: First element `[84]` → already sorted.
- **Pass 2**: Key = 43 → compared with 84 → 43 < 84 → swap → `[43, 84, 21, 62]`.
- **Pass 3**: Key = 21 → compared with 84, 43 → shifts → `[21, 43, 84, 62]`.
- **Pass 4**: Key = 62 → compared with 84 → insert between 43 and 84 → `[21, 43, 62, 84]`.

✅ Sorted array = `[21, 43, 62, 84]`.

---

### **Pseudocode**

```
insertionSort(arr, n):     
	for i = 1 to n-1:         
		key = arr[i]         
		j = i - 1         
		while j >= 0 and arr[j] > key:             
			arr[j+1] = arr[j]             
			j = j - 1         
		arr[j+1] = key
```

---

### **Complexity**

- **Time Complexity**:
    
    - Best: O(n) (already sorted).
    - Average: O(n²).
    - Worst: O(n²) (reverse order).
- **Space Complexity**: O(1) (in-place).

---

### **Advantages**

- Simple to implement.
- Very efficient for **small datasets**.
- Great for **nearly sorted data**.
- Uses **constant extra memory**.

### **Disadvantages**

- Poor performance on **large, randomly ordered datasets**.
- Always quadratic in average/worst case.

---

# 💻 Implementations

---

### **Python**

```python
def insertion_sort(arr):
    for i in range(1, len(arr)):
        key = arr[i]
        j = i - 1
        while j >= 0 and arr[j] > key:
            arr[j + 1] = arr[j]
            j -= 1
        arr[j + 1] = key
    return arr

# Example
arr = [84, 43, 21, 62]
print("Sorted:", insertion_sort(arr))

```

---

### **C++**

```cpp
#include <iostream>
#include <vector>
using namespace std;

void insertionSort(vector<int>& arr) {
    int n = arr.size();
    for (int i = 1; i < n; i++) {
        int key = arr[i];
        int j = i - 1;
        while (j >= 0 && arr[j] > key) {
            arr[j + 1] = arr[j];
            j--;
        }
        arr[j + 1] = key;
    }
}
int main() {
    vector<int> arr = {84, 43, 21, 62};
    insertionSort(arr);
    cout << "Sorted: ";
    for (int x : arr) cout << x << " ";
    cout << endl;
    return 0;
}

```

---

### **Java**

```java
import java.util.Arrays;

public class InsertionSort {
    public static void insertionSort(int[] arr) {
        int n = arr.length;
        for (int i = 1; i < n; i++) {
            int key = arr[i];
            int j = i - 1;
            while (j >= 0 && arr[j] > key) {
                arr[j + 1] = arr[j];
                j--;
            }
            arr[j + 1] = key;
        }
    }
    public static void main(String[] args) {
        int[] arr = {84, 43, 21, 62};
        insertionSort(arr);
        System.out.println("Sorted: " + Arrays.toString(arr));
    }
}

```

---

✅ Now you have:

- **Notes** (explanation, steps, example, complexity, pros & cons)
- **Pseudocode**
- **Code** in Python, C++, and Java