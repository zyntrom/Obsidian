### 🔢 **Matrix Problem: Sum of Squares of Row Sums**

#### 🧮 **Problem Description**

- Input consists of:
    - First line: two integers `m` and `n` → matrix of size `m x n`
    - Followed by `m` lines, each containing `n` integers
- Task:
    
    - For each row, compute the **sum of its elements**
    - Then **square** that row sum
    - Then **sum all** these squared values

![[Pasted image 20250728000728.png]]

#### 📥 **Example Input**

```
3 4 4 7 11 2 1 1 2 4 2 9 0 -1
```

#### 🧾 **Example Output (Step-by-Step)**

1. Row 0 sum: 4 + 7 + 11 + 2 = 24 → 24² = 576
2. Row 1 sum: 1 + 1 + 2 + 4 = 8 → 8² = 64
3. Row 2 sum: 2 + 9 + 0 + (-1) = 10 → 10² = 100
4. Final result: 576 + 64 + 100 = **740**

---

### 🔁 **Looping Logic in C**

#### 🔂 **Inner Loop (per row)**

- For a given row:
    - Initialize `rowsum = 0`
    - Use `colindex` from 0 to `n-1`
    - Read and add each element to `rowsum`
    - After reading all elements:  
        `rowsumsquare = rowsum * rowsum`

#### 🔁 **Outer Loop (per matrix)**

- Iterate over all rows:
    - For each row, call the inner loop
    - Add `rowsumsquare` to a total accumulator, say `squaresum`

---

### 🔄 **Combined Code Logic (Conceptually)**

1. **Initialization:**
    - `rowindex = 0`
    - `squaresum = 0`
2. **Outer Loop** (`while rowindex < m`)
    - `rowsum = 0`
    - `colindex = 0`
3. **Inner Loop** (`while colindex < n`)
    - Read value into `a`
    - `rowsum += a`
    - `colindex++`
4. **After Inner Loop**
    - `rowsumsquare = rowsum * rowsum`
    - `squaresum += rowsumsquare`
    - `rowindex++`
5. **After Outer Loop**
    - Final answer = `squaresum`

---

### 🧪 **Dry Run Example**

**Input:**

```
2 3 1 0 -1 0 1 1
```

- Matrix size: 2 rows, 3 columns

**Execution:**

- Row 0: 1 + 0 + (-1) = 0 → 0² = 0
- Row 1: 0 + 1 + 1 = 2 → 2² = 4
- Final result: **0 + 4 = 4**

---

### ⚠️ **Important Notes**

- Array indices start from 0 in C
- Outer loop tracks `rowindex`
- Inner loop tracks `colindex`
- `rowsum` must be reset to 0 for every new row
- Care must be taken not to let old values affect the next row’s computation