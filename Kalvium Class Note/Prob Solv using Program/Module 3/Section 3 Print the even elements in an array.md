# 📘 Problem: Print the Even Elements in an Array

### Problem Statement:

- Initialize an array of size 10.
- Print only the **even elements** from the array.

### Example:

Input:  
`2 3 4 5 6 7 8 9 3 7`

Output:  
`2 4 6 8`

---

## 🔑 Concepts Used:

- **For loop** → to iterate through array elements.
- **If statement** → to check whether an element is even (`element % 2 == 0`).

---

## 📝 Approach:

1. Read/initialize an array of size 10.
2. Loop through each element.
3. Check if the element is divisible by 2.
4. If yes → print the element.

---

## 💻 Code Implementations

### ✅ cpp Code

```cpp
#include <iostream> 
using namespace std;  
int main() {     
	int arr[10] = {2, 3, 4, 5, 6, 7, 8, 9, 3, 7};      
	cout << "Even elements: ";     
	for (int i = 0; i < 10; i++) {         
		if (arr[i] % 2 == 0) {             
			cout << arr[i] << " ";         
		}     
	}     
	cout << endl;     
	return 0; 
}

```
---

### ✅ Python Code

```python
arr = [2, 3, 4, 5, 6, 7, 8, 9, 3, 7]  
print("Even elements:", end=" ") 
for num in arr:     
	if num % 2 == 0:         
		print(num, end=" ")
```

---

### ✅ Java Code

```java
public class EvenElements {     
	public static void main(String[] args) {         
		int[] arr = {2, 3, 4, 5, 6, 7, 8, 9, 3, 7};
		System.out.print("Even elements: ");         
		for (int i = 0; i < arr.length; i++) {             
			if (arr[i] % 2 == 0) {    
				System.out.print(arr[i] + " ");             
			}         
		}     
	} 
}
```