# 🧠 Introduction to Recursion

---

## 🌍 1. What is Recursion?

**Definition:**  
Recursion is a programming technique where a **function calls itself** to solve **smaller versions of the same problem**, until it reaches a **base case** (stopping condition).

It’s like **breaking a big problem into smaller, identical problems**.

---

### 🧩 Analogy 1 — Nested Boxes

Imagine you have a **series of boxes**, one inside another, and the key is in the smallest box.  
To find the key:

1. Open the first box
2. Inside, you find another box — repeat the same process
3. Continue until you reach the smallest box containing the key

This is **recursion** — solving a problem by repeatedly applying the same logic to smaller instances.

---

### 🪞 Analogy 2 — Mirrors Facing Each Other

If you stand between two mirrors, your reflection appears **repeated infinitely** — this is how recursion works:  
A function “reflects” itself repeatedly until a **base condition** stops it.

---

### 💡 Key Idea

In recursion:

- Each recursive call **reduces** the problem size
- There is always a **base case** (a simple version that doesn’t call itself)

If there is **no base case**, recursion will continue **infinitely**, leading to a **stack overflow error**

---

### ⚙️ Example: Factorial of n (n!)

**Mathematical Definition:**  
n! = n × (n - 1)!  
Base case: 0! = 1

#### Step-by-step logic:

1. factorial(3) = 3 × factorial(2)
2. factorial(2) = 2 × factorial(1)
3. factorial(1) = 1 × factorial(0)
4. factorial(0) = 1 (base case)

Now it “unwinds”:  
3 × 2 × 1 × 1 = 6

---

### 💻 Code Example: Factorial using Recursion

#### Java:

```java
public class Factorial {  
	static int factorial(int n) {  
		if (n == 0)  
			return 1; // base case  
		return n * factorial(n - 1); // recursive call  
}
public static void main(String[] args) {
	System.out.println(factorial(5)); // Output: 120 }
}
```

#### C++:

```cpp
include <iostream>  
using namespace std;

int factorial(int n) {  
	if (n == 0)  
		return 1; // base case  
	return n * factorial(n - 1); // recursive call  
}

int main() {  
	cout << factorial(5);  
	return 0;  
}

```
#### Python:

```python
def factorial(n):  
	if n == 0:  
		return 1 # base case  
	return n * factorial(n - 1) # recursive call

print(factorial(5))
```

---

## 🧭 2. Types of Recursion

Recursion is classified based on **how the function calls itself**.

---

### 1️⃣ Direct Recursion

A function **calls itself directly**.

Example:  
f() → f()

#### Code Example:

```cpp
int f(int n) {  
	if (n == 0) return 0;  
	return f(n - 1) + n;  
}
```

---

### 2️⃣ Indirect Recursion

A function **calls another function**, which then calls the first one back.

Example:  
A() → B() → A()

#### Code Example:

```cpp
void A(int n);  
void B(int n);

void A(int n) {  
	if (n <= 0) return;  
	cout << n << " ";  
	B(n - 1);  
}

void B(int n) {  
	if (n <= 0) return;  
	cout << n << " ";  
	A(n / 2);  
}
```

---

### Subtypes of Recursion (Common Forms):

|Type|Description|Example|
|---|---|---|
|Tail Recursion|Last statement is recursive call|Factorial (iterative version)|
|Head Recursion|Recursive call happens first|Printing in reverse order|
|Tree Recursion|Function calls itself more than once|Fibonacci|
|Nested Recursion|Function passes recursive call as argument|Ackermann function|

---

### 🌳 Example: Fibonacci Series (Tree Recursion)

f(n) = f(n-1) + f(n-2)

#### Code (Python):

def fib(n):  
if n <= 1:  
return n  
return fib(n-1) + fib(n-2)

print(fib(5)) # Output: 5

#### Recursive Tree Expansion:

fib(5)  
= fib(4) + fib(3)  
= (fib(3)+fib(2)) + (fib(2)+fib(1))  
→ many overlapping subproblems → **Exponential complexity**

---

## 🧠 3. Base Case in Recursion

**Base case** = stopping condition for recursion.  
Without a base case → infinite recursion → stack overflow.

### Example:

def countdown(n):  
if n == 0: # base case  
print("Blast Off!")  
return  
print(n)  
countdown(n-1)

countdown(5)

Output: 5 4 3 2 1 Blast Off!

---

## ⚡ 4. Time Complexity in Recursion

The **time complexity** of a recursive function depends on:

- Number of recursive calls
    
- Work done per call
    

---

### 🔢 Example 1: Factorial

T(n) = T(n - 1) + O(1)  
→ O(n)

### 🔢 Example 2: Fibonacci

T(n) = T(n - 1) + T(n - 2) + O(1)  
→ O(2ⁿ) (Exponential)

---

### 💡 Trick for Complexity:

If recurrence is:

- T(n) = T(n-1) + c → O(n)
    
- T(n) = 2T(n/2) + c → O(n log n)
    
- T(n) = T(n/2) + c → O(log n)
    

---

## 🧩 5. When to Use Recursion

Ask these **three questions**:

---

### 1️⃣ Can the problem be divided into smaller subproblems?

If yes → good candidate for recursion.  
🧠 Example: Factorial, Fibonacci, Binary Search

---

### 2️⃣ Is there a Base Case?

You must have a condition where recursion **stops**.  
🧠 Example: factorial(0) = 1

---

### 3️⃣ Do subproblems follow the same logic?

If yes, recursion fits well.  
🧠 Example: Sorting algorithms (Merge Sort, Quick Sort)

---

## 🧩 Example: QuickSort Recursion

### Steps:

1. Pick a pivot
    
2. Divide array into two parts (less than pivot, greater than pivot)
    
3. Recursively sort both parts
    

#### Python:

def quicksort(arr):  
if len(arr) <= 1:  
return arr # base case  
pivot = arr[0]  
left = [x for x in arr[1:] if x <= pivot]  
right = [x for x in arr[1:] if x > pivot]  
return quicksort(left) + [pivot] + quicksort(right)

print(quicksort([3,6,1,8,2]))

---

## ⚙️ 6. Recursion vs Iteration

|Feature|Recursion|Iteration|
|---|---|---|
|Definition|Function calls itself|Loop repeats block of code|
|Base case|Must exist|Loop condition|
|Memory|Uses call stack|Uses single variable|
|Performance|Slower (stack overhead)|Faster|
|Simplicity|Cleaner for divide-and-conquer|Better for simple tasks|

---

### Example Comparison: Factorial

#### Iterative:

int fact = 1;  
for(int i = 1; i <= n; i++) fact *= i;

#### Recursive:

if (n == 0) return 1;  
else return n * fact(n-1);

---

## 🗺️ 7. Mind Map Summary

**Recursion**

`Recursion ├── Definition: Function calls itself ├── Components: │   ├── Base Case │   ├── Recursive Step │ ├── Types: │   ├── Direct │   ├── Indirect │   ├── Tail / Head / Tree / Nested │ ├── Examples: │   ├── Factorial │   ├── Fibonacci │   ├── QuickSort │   ├── Tower of Hanoi │ └── Complexity:     ├── Factorial → O(n)     ├── Fibonacci → O(2ⁿ)`

---

## 🧩 8. Key Points for Exam

- Recursion = function calling itself
    
- Must have **base case** (stopping condition)
    
- Breaks large problems into **smaller identical subproblems**
    
- Use recursion when:
    
    - Problem is **naturally repetitive**
        
    - Problem can be **broken into similar subproblems**
        
- Analyze time complexity using **recurrence relations**
    

---

## 📚 9. Bonus Resources

- Medium: Getting Started with Recursion
    
- MIT Lecture: Introduction to Recursion
    
- [YouTube: Solve Problems using Recursion](https://youtube.com)
    
- [YouTube: Time & Space Complexity in Recursive Programs](https://youtube.com)
    
- LeetCode Practice Problems on Recursion
    

---

✅ **Pro Tip:**  
If a problem:

- Has a base case
    
- Can be divided into smaller identical problems  
    → Recursion is ideal!
    

---