## 🧮 **Computing the Trace of a Matrix Using `for` Loop in C**

### 🔹 **Context**

- Previously used `while` and `do-while` loops (including nested loops).
- Now demonstrating **nested `for` loops** for matrix problems.
- `for` loops are well-suited when the **number of iterations is known in advance**, which is often the case with matrices.

---

## 📌 **Problem Statement**

- First input line contains an integer `n` → size of the matrix.
- The matrix is of size **`n × n`**.
- The next `n` lines contain `n` floating point numbers each (i.e., matrix entries **row by row**).
- **Goal**: Compute the **trace** of the matrix (sum of diagonal elements).

> ✅ **Trace** is the sum of all elements `a[i][j]` where `i == j`.

---

## 🧠 **How Trace is Computed by Hand**

Given matrix:

```
1 2 3 4 5 6 7 8 9
```

Trace = `1 (row 0, col 0)` + `5 (row 1, col 1)` + `9 (row 2, col 2)` = **15**

Only the diagonal elements (where row index = column index) are summed.

---

## 🧰 **Variables Used**

- `int i, j` → loop counters for rows and columns
    
- `int n` → matrix size
    
- `float a` → current matrix element
    
- `float trace = 0;` → accumulator for the sum of diagonal elements
    

---

## 🧾 **Program Flow**

1. **Input**: Read `n` (size of matrix).
    
2. Use **nested `for` loops**:
    
    - Outer loop: iterate over rows (`i = 0; i < n; i++`)
        
    - Inner loop: iterate over columns (`j = 0; j < n; j++`)
        
    - Inside the inner loop:
        
        - Read each matrix element `a`.
            
        - If `i == j` (diagonal), add `a` to `trace`.
            

---

## 🧪 **Sample Matrix Input**

diff

CopyEdit

`3 2 0 -1 1 3 4 -1 0 1`

### 📊 Matrix:

css

CopyEdit

`[2,  0, -1] [1,  3,  4] [-1, 0,  1]`

### 📈 Trace Calculation:

- Row 0, Col 0 → 2 ✅
    
- Row 1, Col 1 → 3 ✅
    
- Row 2, Col 2 → 1 ✅  
    **Trace = 2 + 3 + 1 = 6**
    

---

## 💡 **C Language Notes**

- Braces `{}` are **optional** for `if` blocks with only **one statement**.
    

c

CopyEdit

`if (i == j)     trace += a;`

- This is valid and **common** in C style.
    

---

## 🔁 **Why `for` Loops Are Ideal Here**

- Matrix size is **known beforehand** → makes it easier to plan iterations.
    
- Loop counters (`i` and `j`) are naturally suited for `for` loop structure.
    
- More **compact and readable** than using `while`.
    

---

## ✅ **Program Summary**

- Initialize `trace = 0`.
    
- Use nested `for` loops:
    
    - Read elements row-wise.
        
    - Check if diagonal → add to `trace`.
        
- Final result: trace value is stored in `trace`.