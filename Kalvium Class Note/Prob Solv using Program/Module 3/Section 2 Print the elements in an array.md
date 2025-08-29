### ✅ C++ Program

```cpp
#include <iostreamwd>
using namespace std;

int main() {
    int n;
    cin >> n;  // read array size
    int arr[n];  // declare array of size n
    for (int i = 0; i < n; i++) {
        cin >> arr[i];  // read array elements
    }
    for (int i = 0; i < n; i++) {
        cout << arr[i] << " ";  // print elements
    }
    return 0;
}
```

---

### ✅ Java Program

```java
import java.util.Scanner;  
public class Main {     
	public static void main(String[] args) {         
		Scanner sc = new Scanner(System.in);          
		int n = sc.nextInt(); // read array size         
		int[] arr = new int[n];          
		for (int i = 0; i < n; i++) {             
			arr[i] = sc.nextInt(); // read elements         
		}          
		for (int i = 0; i < n; i++) {             
			System.out.print(arr[i] + " "); // print elements         
		}     
	} 
}
```

---

### ✅ Python Program

```python
n = int(input())  # read array size 
arr = list(map(int, input().split()))  # read array elements  
print(*arr)  # print elements space-separated
```

---

### 🔑 Key Points

- Input:
    - First line → size of array `n`
    - Second line → `n` integers
- Output: print them in the same order, space-separated.
- Constraint: elements are integers between `-10^5` and `10^5`.