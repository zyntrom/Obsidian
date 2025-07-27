### 🔷 **Problem Description**

- Goal: **Identify Pythagorean triples** from a stream of integers.
- A **Pythagorean triple** consists of three positive integers (a, b, c) such that:
```
a2+b2=c2
```

Example: (3, 4, 5)

---

### 🔷 **Input Format**

- First input: An integer `n` (n ≥ 2), the number of integers to follow.
- Next `n` integers: These are the values from which we must identify **Pythagorean triples**.
- **Note**: Only **positive integers** are considered for forming triples. Negative numbers are to be **skipped** using the `continue` statement.

---

### 🔷 **Consecutive Positive Numbers**

- Triples must be formed from **consecutive positive numbers**, ignoring any negative values in between.
    
- Example Input:
```
    8 -1 3 -2 4 5 -3 -4 6
```
    - Here, 3, 4, 5 are **consecutive positive numbers**, forming a valid Pythagorean triple.

---

### 🔷 **Approach / Algorithm**

1. **Variables Used**:
    - `current`: currently read number.
    - `prev`: previous positive number.
    - `prev2`: second previous positive number.
    - `count`: counts how many **positive numbers** have been seen.
    - `n`: total number of numbers to read.
    - `i`: loop counter to control reading `n` inputs.
2. **Input Reading**:
    
    - Use a `for` loop running `n` times to read inputs.
    - For each read input:
        - If the number is **non-positive**, use `continue` to skip the iteration.
3. **Handling First Two Positive Numbers**:
    - If it is the **first** positive number: store it in `prev2`, increment count to 1.
    - If it is the **second** positive number: store it in `prev`, increment count to 2.
4. **Handling Subsequent Positive Numbers**:
    - From the **third positive number** onward:
        - You now have a triple: `prev2`, `prev`, `current`.
        - Check if:
            prev2^2 + prev^2  = current^2
        - If true, print the Pythagorean triple.
5. **Shifting the Window**:
    - After processing a triple:
        - `prev2 = prev`
        - `prev = current`
    - This maintains the **sliding window of 3 consecutive positive numbers**.

---

### 🔷 **Use of `continue`**

- The `continue` statement is used **to skip non-positive numbers** without doing further processing in the current iteration.
- This keeps the logic clean and avoids nested `if` conditions.

---

### 🔷 **Advantages Highlighted**

- `continue` helps **simplify code readability**, especially when you want to **ignore specific values early** in a loop.
- Eliminates the need for **extra nested `if` blocks**.

---

### 🔷 **Edge Conditions**

- At least **2 positive numbers** must be encountered before a triple can be checked.
- If there are **not enough positive numbers**, no triple will be printed.