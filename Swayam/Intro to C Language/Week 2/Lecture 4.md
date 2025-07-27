## ✅ **Lecture Summary: Finding the Longest Contiguous Increasing Subsequence**

---

### 🧠 **Problem Statement**

> **Given a sequence of integers (terminated by -1), output the length of the longest contiguous increasing subsequence (LCIS).**

- **Contiguous**: Elements must be adjacent in input.
- **Increasing**: Each next number is strictly greater than the previous one.
- **Example Input**: `9 2 4 0 3 4 6 9 2 -1`  
    ➤ LCIS is `0 3 4 6 9` → **Length: 5**

---

### 🔁 **Approach (using loops)**

- Continuously read numbers until `-1` is encountered.
- Track the current subsequence and update the **maximum length** when the current one ends.

---

### 🧮 **Variables Used**

|Variable|Meaning|
|---|---|
|`c`|Current number being read|
|`p`|Previous number|
|`length`|Length of current increasing subsequence|
|`maxlen`|Length of longest subsequence found so far|

---

### ⚙️ **Logic Outline**

1. **Initialize**:
    - Read the first number → `p`
    - Set `length = 1`, `maxlen = 1`
2. **Loop**:
    - Read next number → `c`
    - If `c == -1` → stop
    - If `c > p`:
        - It's increasing → `length += 1`
    - Else:
        - Not increasing → reset `length = 1`
    - After each step → update `maxlen = max(maxlen, length)`
    - Shift pointers: `p = c`
3. **After loop ends**:
    - Print `maxlen`

---

### 🧪 **Example Tracing**

**Input**: `11 9 7 8 11 12 15 15 -1`
- `11 → 9 → 7`: not increasing
- `7 → 8 → 11 → 12 → 15`: increasing (length 5)
- `15 → 15`: not increasing  
    ➤ **Output**: `5`

---

### 🧠 **Key Concepts**

- **Contiguous**: Subsequence ends as soon as `c ≤ p`
- **Tracking Two Numbers**: You need both previous (`p`) and current (`c`) to compare
- **Pointer Movement**:
    - After comparison, **advance both**: set `p = c` and read new `c`
- **Length Reset**: When sequence breaks, start fresh from 1

---

### 🧪 **Sample Dry Run Snippet**

```c
int p, c, length = 1, maxlen = 1; 
scanf("%d", &p);  // Read first number  
while (1) {     
	scanf("%d", &c);     
	if (c == -1) break;     
	if (c > p)         
		length++;     
	else         
		length = 1;     
	if (length > maxlen)         
		maxlen = length;     
		p = c; 
	}  printf("Length of longest increasing contiguous subsequence is %d\n", maxlen);
```

---

### 📌 **Final Notes**

- This problem is excellent for understanding **loop control**, **condition-based resets**, and **tracking running max**.
    
- You will likely implement this as a full program in the next part.