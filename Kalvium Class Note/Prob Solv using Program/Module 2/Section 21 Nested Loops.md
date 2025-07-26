## 🔁 **Nested Loops** – SPE 2025

### 🧠 **What is a Nested Loop?**

A **nested loop** is a loop inside another loop.  
Think of it like trying every **topping** on every **flavor of donut** — one loop for donut types, another for toppings.

👉 Used in:

- Pattern printing
- Matrix/grid processing
- Combinations/permutations
- Game logic (e.g., 2D boards)

---

### 🔄 **Basic Structure**

#### ✅ Python Example:

```python
for i in range(1, 4):     
	for j in range(1, 4):         
		print(f"i = {i}, j = {j}")
```

#### ✅ C++ Example:

```c++
for (int i = 1; i <= 3; ++i) {     
	for (int j = 1; j <= 3; ++j) {         
		cout << "i = " << i << ", j = " << j << endl;    
	}
}
```

---

### 🧾 **Explanation of Output**

- Outer loop (`i`) runs from 1 to 3.
- For each `i`, the inner loop (`j`) runs from 1 to 3.
- Each pair of `(i, j)` is printed.

#### ✅ Output:


```
i = 1, j = 1 
i = 1, j = 2 
i = 1, j = 3 
i = 2, j = 1 
i = 2, j = 2 
i = 2, j = 3 
i = 3, j = 1 
i = 3, j = 2 
i = 3, j = 3
```

---

### ⚠️ Notes & Tips

|Language|Loop Range|Note|
|---|---|---|
|Python|`range(1, 4)`|Runs 1 to 3 (`4` not included)|
|C++|`i <= 3`|Runs from 1 to 3 inclusive|

✅ You can nest:

- `for` inside `for`
- `while` inside `while`
- `for` inside `while` or vice versa

---

### 🧠 Why Use Nested Loops?

|Use Case|Example|
|---|---|
|Pattern generation|Printing stars/grids|
|Matrix operations|Traversing 2D arrays|
|Combinatorics|All pair combinations|
|Game development|Tic-Tac-Toe logic|