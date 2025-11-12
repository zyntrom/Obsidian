## 🧠 Problem

**Goal**: Print numbers from `n` to `1` in reverse order.

**Input**: A single integer `n`  
**Output**: Space-separated numbers from `n` to `1`

---

## 🧮 Logic & Approach

- We need to loop **from n down to 1**
- Use a `for` loop:
    - Start at `n`
    - End at `1` (inclusive)
    - Step by `-1` (decrement)

---

## 🐍 Python Program

```python
n = int(input())  # Input number 
for i in range(n, 0, -1):     
	print(i, end=" ")
```

### 🔍 Explanation

- `range(n, 0, -1)` → starts at `n`, stops **before** `0`, steps down by `1`
- `end=" "` → prints on the same line with a space

---

## 💻 cpp Program

```cpp
#include <iostream> 
using namespace std;  
int main() {     
	int n;     
	cin >> n; // Input number     
	for (int i = n; i >= 1; i--) {         
		cout << i << " ";     
	}     
	return 0; 
}
```

### 🔍 Explanation

- `for (int i = n; i >= 1; i--)` → start at `n`, loop until `i == 1`, decrease `i` by 1

---

## ✅ Sample Input & Output

**Input**

```
4
```

**Output**

```
4 3 2 1
```