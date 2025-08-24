## Problem

**Task:**  
Take an integer input `n` (size of array) and swap the **first** and **last** element of the array.

**Example:**  
Input:  
```
6  
1 2 3 4 5 6
```

Output:  
```
6 2 3 4 5 1
```

---

## Approach

1. Read the size `n` of the array.
2. Read `n` integers into an array.
3. Store the **first element** in a temporary variable `temp`.
4. Assign the **last element** to the first position.
5. Assign `temp` (original first element) to the last position.
6. Print the modified array.

---

## C++ Solution

```c++
#include <iostream>
using namespace std;
int main() {
    int n;
    cin >> n;
    int arr[n];
    for (int i = 0; i < n; i++) {
        cin >> arr[i];
    }
    // Swap first and last
    int temp = arr[0];
    arr[0] = arr[n - 1];
    arr[n - 1] = temp;
    // Print result
    for (int i = 0; i < n; i++) {
        cout << arr[i] << " ";
    }
    return 0;
}

```

---

## Python Solution (Universal way, no shortcuts)

```python
# Read size of array
n = int(input())

# Read array elements
arr = list(map(int, input().split()))

# Swap first and last using temp variable
temp = arr[0]
arr[0] = arr[n - 1]
arr[n - 1] = temp

# Print the result
for i in range(n):
    print(arr[i], end=" ")

```

---

## Java Solution

```java
import java.util.Scanner;
public class SwapFirstLast {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[] arr = new int[n];
        for (int i = 0; i < n; i++) {
            arr[i] = sc.nextInt();
        }
        
        // Swap first and last
        int temp = arr[0];
        arr[0] = arr[n - 1];
        arr[n - 1] = temp;
        
        // Print result
        for (int i = 0; i < n; i++) {
            System.out.print(arr[i] + " ");
        }
    }
}

```