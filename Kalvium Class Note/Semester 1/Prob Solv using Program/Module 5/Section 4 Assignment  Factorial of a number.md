# 🧠 Assignment: Factorial of a Number

---

## 🌍 1. Problem Statement

Write a program to calculate the **factorial of a number `n`** using **direct recursion**.
**Input:**
- Integer `n` (0 ≤ n ≤ 12)
**Output:**
- Factorial of `n` (n!)
**Definition of Factorial:**
- n! = n × (n-1) × (n-2) × ... × 1
- 0! = 1 (base case)

**Example:**
- 5! = 5 × 4 × 3 × 2 × 1 = 120
- 0! = 1

---

## ⚙️ 2. How to Approach

1. **Base Case:**
    - If n == 0 → return 1
2. **Recursive Step:**
    - For n > 0 → return n × factorial(n-1)
3. **Return Result:**
    - Recursion unwinds step by step, multiplying the values

---

## 🌳 3. Recursion Tree Example (n = 4)

```cpp
         fact(4)
        /       \
      4 *      fact(3)
               /       \
            3 *      fact(2)
                   /       \
                2 *      fact(1)
                       /       \
                    1 *      fact(0)
                           /
                         1 (Base Case)

```

**Breakdown of Calls:**

- fact(4) calls fact(3) → fact(2) → fact(1) → fact(0)
- fact(0) returns 1 (base case)
- Recursion unwinds: 1 → 1×1 → 2×1 → 3×2 → 4×6 = 24

---

## 🧮 4. Dry Run of Factorial Recursion (fact(4))

|Function Call|Returns|
|---|---|
|fact(4) → 4 * fact(3)|4 * 6 = 24|
|fact(3) → 3 * fact(2)|3 * 2 = 6|
|fact(2) → 2 * fact(1)|2 * 1 = 2|
|fact(1) → 1 * fact(0)|1 * 1 = 1|
|fact(0)|1 (Base Case)|

---

## 💻 5. Universal Recursive Code (Java / C++ / Python)

**Logic is identical in all three languages.** Replace syntax as needed.

```java
// Java
int factorial(int n) {
    if (n == 0) return 1; // Base case
    return n * factorial(n - 1); // Recursive call
}

// Usage:
int n = 5;
System.out.println(factorial(n));

```

```cpp
// C++
int factorial(int n) {
    if (n == 0) return 1; // Base case
    return n * factorial(n - 1); // Recursive call
}

// Usage:
int n = 5;
cout << factorial(n);

```

```python
# Python
def factorial(n):
    if n == 0:
        return 1  # Base case
    return n * factorial(n - 1)  # Recursive call

# Usage:
n = 5
print(factorial(n))

```

**Steps are exactly the same:**

1. Check base case
2. Recursively multiply n × factorial(n-1)
3. Return result

---

## ⚡ 6. Example Runs

**Example 1:**

Input: 5  
Output: 120

**Example 2:**

Input: 0  
Output: 1

---

## 🧩 7. Time and Space Complexity

|Factor|Complexity|
|---|---|
|Time|O(n) → Each number from n down to 0 is multiplied|
|Space|O(n) → Recursion stack stores n calls|

**Limitation:**

- Recursion uses stack memory
- For large n (>12 for int), factorial may **overflow**
- Optimization: Use **iterative method** or **BigInteger (Java) / long long (C++) / arbitrary-precision int (Python)**

---

## 🗺️ 8. Mind Map Summary

```
Factorial(n)
├── Base Case
│   └── n == 0 → return 1
├── Recursive Case
│   └── n * factorial(n-1)
├── Recursion Tree Example
│   └── fact(4)
├── Dry Run
│   └── Stepwise multiplication
├── Complexity
│   ├── Time → O(n)
│   └── Space → O(n)
└── Limitation
    └── Large n → risk of integer overflow

```

---

## 📚 9. Bonus Resources

- [Factorial Coding in Python](https://youtube.com)
- [Factorial Coding in C++](https://youtube.com)
- [Factorial Coding in Java](https://youtube.com)

---

✅ **Pro Tip:**

- Identify **base case first**, then **recursive formula**, then **dry run small examples**.
- Iterative solutions are often safer for very large n due to recursion stack limits.