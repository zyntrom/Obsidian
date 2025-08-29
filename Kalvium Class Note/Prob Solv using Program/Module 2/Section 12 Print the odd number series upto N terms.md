## 🧠 Problem

**Goal**: Print the first `N` odd numbers starting from 1.

**Input**: A single integer `n`  
**Output**: First `n` odd numbers separated by spaces

---

## 🧮 Logic & Approach

- Odd numbers start from 1, then 3, 5, 7, 9...
- These are in the form: `2*i + 1 - 1` or simply `2*i + 1 - 2` if `i` starts from 1
- But most simply, use: `2*i - 1` for `i` from 1 to `n`

So, loop from `1` to `n`, and for each `i`, print `2*i - 1`

---

## 🐍 Python Program

```python
n = int(input())  # Number of odd terms 
for i in range(1, n + 1):     
	print(2 * i - 1, end=" ")
```

### 🔍 Explanation

- `range(1, n + 1)` → loops `i` from `1` to `n`
- `2 * i - 1` gives the `i-th` odd number

---

## 💻 cpp Program

```cpp
#include <iostream> 
using namespace std;  
int main() {     
	int n;     
	cin >> n;  // Number of odd terms     
	for (int i = 1; i <= n; i++) {         
		cout << 2 * i - 1 << " ";     
	}     
	return 0; 
}
```

### 🔍 Explanation

- `2 * i - 1` → prints the `i-th` odd number
- Loop from `1` to `n` inclusive

---

## ✅ Sample Input & Output

**Input**

```
5
```

**Output**

```
1 3 5 7 9
```