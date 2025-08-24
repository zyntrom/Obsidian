## 📝 Problem Notes

**Problem:**

- You are given an array of integers.
- Find the largest and smallest elements.
- Swap them in the array.
- Print the modified array.

**Key Points:**

- Use a loop to find the index of the minimum and maximum element.
- Swap their positions.
- Print the final array.

**Concepts Used:**

- Arrays
- For loop
- If condition
- Swapping elements

---

## ✅ Solutions

### C++ Solution

```c++
#include <iostream> 
using namespace std;  
int main() {     
	int n;     
	cin >> n; // size of array     
	int arr[n];      // Input array     
	for (int i = 0; i < n; i++) {         
		cin >> arr[i];     
	}      
	// Find index of min and max     
	int minIndex = 0, maxIndex = 0;     
	for (int i = 1; i < n; i++) {         
		if (arr[i] < arr[minIndex]) minIndex = i;         
		if (arr[i] > arr[maxIndex]) maxIndex = i;     
	}      
	// Swap     
	int temp = arr[minIndex];     
	arr[minIndex] = arr[maxIndex];     
	arr[maxIndex] = temp;      
	// Print result     
	for (int i = 0; i < n; i++) {         
		cout << arr[i] << " ";     
	}      
	return 0; 
}
```

---

### Python Solution

```python
# Swap largest and smallest element in an array
# Input
n = int(input())                # size of array
arr = list(map(int, input().split()))

# Step 1: Find index of smallest and largest
min_index = 0
max_index = 0

for i in range(1, n):
    if arr[i] < arr[min_index]:
        min_index = i
    if arr[i] > arr[max_index]:
        max_index = i

# Step 2: Swap smallest and largest
temp = arr[min_index]
arr[min_index] = arr[max_index]
arr[max_index] = temp

# Step 3: Print result
for i in range(n):
    print(arr[i], end=" ")

```

---

### Java Solution

```java
import java.util.Scanner;
public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt(); // size of array
        int[] arr = new int[n];
        // Input
        for (int i = 0; i < n; i++) {
            arr[i] = sc.nextInt();
        }
        // Find index of min and max
        int minIndex = 0, maxIndex = 0;
        for (int i = 1; i < n; i++) {
            if (arr[i] < arr[minIndex]) minIndex = i;
            if (arr[i] > arr[maxIndex]) maxIndex = i;
        }
        // Swap
        int temp = arr[minIndex];
        arr[minIndex] = arr[maxIndex];
        arr[maxIndex] = temp;
        // Print
        for (int i = 0; i < n; i++) {
            System.out.print(arr[i] + " ");
        }
    }
}

```