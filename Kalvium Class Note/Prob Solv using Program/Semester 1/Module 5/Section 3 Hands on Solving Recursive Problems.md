# 🧠 Hands-on: Solving Recursive Problems — Fibonacci Series

---

## 🌍 1. Problem Statement

Write a program that prints the **Fibonacci series** up to the **nth term** (0-based indexing).

**Input:**

- Integer `n` representing the number of Fibonacci terms

**Output:**

- Space-separated Fibonacci numbers up to the nth term

**Fibonacci Definition:**

- F(0) = 0
- F(1) = 1
- F(n) = F(n-1) + F(n-2), for n ≥ 2

---

## ⚙️ 2. How to Approach

1. **Define a Recursive Function:**  
    Create `fib(n)` that returns the nth Fibonacci number.
2. **Base Cases:**
    - If n = 0 → return 0
    - If n = 1 → return 1
3. **Recursive Step:**
    - For n ≥ 2 → return `fib(n-1) + fib(n-2)`
4. **Iterate & Print:**
    - Loop from i = 0 to n
    - Call `fib(i)` for each i and print the value

---

## 🌳 3. Recursion Tree Example (n = 4)

```cpp
               F(4)
              /    \
         F(3)      F(2)
        /    \     /    \
    F(2)    F(1) F(1)   F(0)
   /    \
F(1)   F(0)

```

**Breakdown:**

- F(4) calls F(3) and F(2)
- F(3) calls F(2) and F(1)
- F(2) calls F(1) and F(0)
- Base cases stop recursion (F(1) = 1, F(0) = 0)

---

## 🧮 4. Dry Run (F(4))

|Function Call|Returns|
|---|---|
|F(4) → F(3)+F(2)|2 + 1 = 3|
|F(3) → F(2)+F(1)|1 + 1 = 2|
|F(2) → F(1)+F(0)|1 + 0 = 1|
|F(1)|1 (Base case)|
|F(0)|0 (Base case)|

---

## 💻 5. Code Implementation

### Java

```java
public class Fibonacci {  
	static int fib(int n) {  
	if (n == 0) return 0; // Base case  
	if (n == 1) return 1; // Base case  
	return fib(n-1) + fib(n-2); // Recursive step  
}

	public static void main(String[] args) {     
		int n = 5;     
		for (int i = 0; i <= n; i++) {         
			System.out.print(fib(i) + " ");     
		} 
	}
}
```

---

### C++

```c++
include <iostream>  
using namespace std;

int fib(int n) {  
	if (n == 0) return 0; // Base case  
	if (n == 1) return 1; // Base case  
	return fib(n-1) + fib(n-2); // Recursive step  
}

int main() {  
	int n = 5;  
	for (int i = 0; i <= n; i++) {  
		cout << fib(i) << " ";  
	}  
}
```

---

### Python

```python
def fib(n):  
	if n == 0:  
		return 0 # Base case  
	if n == 1:  
		return 1 # Base case  
	return fib(n-1) + fib(n-2) # Recursive step

n = 5  
for i in range(n+1):  
	print(fib(i), end=" ")
```

---

## ⚡ 6. Example Runs

**Example 1:**

Input: 5  
Output: 0 1 1 2 3 5

**Example 2:**

Input: 3  
Output: 0 1 1 2

**Explanation:**

- Start with F(0)=0, F(1)=1
- Each next term = sum of previous two terms

---

## 🧩 7. Important Notes

- **Time Complexity:** O(2ⁿ) — exponential due to overlapping subproblems
- **Space Complexity:** O(n) due to recursion stack
- **Limitation:** Slow for large n → use **Dynamic Programming** / **Memoization** for optimization

---

## 🌟 8. Optimization (Optional)

### Memoized Fibonacci (Python Example):

```python
memo = {}  
def fib(n):  
	if n in memo:  
		return memon  
	if n == 0: 
		return 0  
	if n == 1: 
		return 1  
	memon = fib(n-1) + fib(n-2)  
	return memon
```

---

## 🗺️ 9. Mind Map Summary

**Fibonacci Recursion**

```
Fibonacci(n)
├── Base Cases
│   ├── F(0) = 0
│   └── F(1) = 1
├── Recursive Case
│   └── F(n) = F(n-1) + F(n-2)
├── Recursion Tree Example
│   └── F(4) expansion
├── Dry Run
│   └── Stepwise calculation
├── Complexity
│   ├── Time → O(2ⁿ)
│   └── Space → O(n)
└── Optimization
    └── Memoization / DP
```

---
```embed
title: "Recursion for Beginners - Fibonacci Numbers"
image: "https://i.ytimg.com/vi/dDokMfPpfu4/maxresdefault.jpg"
description: "🚀 https://neetcode.io/ - A better way to prepare for Coding Interviews🥷 Discord: https://discord.gg/ddjKRXPqtk🐦 Twitter: https://twitter.com/neetcode1🐮 S..."
url: "https://youtu.be/dDokMfPpfu4"
favicon: ""
aspectRatio: "56.25"
```

## 📚 10. Resources

- Fibonacci Sequence Explanation & Coding
- LeetCode: Fibonacci Problems
- [YouTube: Fibonacci Recursive Solutions](https://youtube.com)

---

✅ **Pro Tip:**  
Always identify the **base case first**, then implement the **recursive formula**, and finally **dry run** for small examples to ensure correctness.