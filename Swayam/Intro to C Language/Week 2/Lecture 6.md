## **Topic: Finding Longest Increasing Contiguous Subsequence – Trace and Final Check**

### **Key Concept**

- We are tracing the logic of a program that finds the **longest increasing contiguous subsequence** in a list of numbers.
- Input ends with a sentinel value `-1`.
- The logic must account for the possibility that the longest increasing subsequence occurs **at the end** of the input.

---

### **General Idea**

- The logic tracks a sequence of increasing numbers.
- When the current number is **less than or equal to** the previous number, it means the increasing sequence has **broken**.
- At that break:
    - Check if the **just-ended** sequence was the **longest so far**.
    - If so, update the `maxLength`.
    - Then reset `length = 1` for the new sequence.

---

### **Important Final Check**

- If the **longest increasing sequence ends at the end of the input**, then it won’t be caught in the loop.
- Hence, **after the loop ends**, check again:
    - If the final `length` is **greater than** `maxLength`, then update `maxLength`.
- This is handled by a **small `if` block** at the end of the loop.

---

### **Tracing Example Input**

- **Input**: `3 2 1 3 5 -1`
- Goal: Trace how the program identifies the longest increasing contiguous subsequence.

#### **Step-by-Step Execution**

1. **Initialization**:
    - `length = 0`
    - `maxLength = 0`
    - `previous`, `current` are undefined.
2. **First number (`3`)**:
    - `previous = 3`
    - Not `-1`, so enter main logic.
    - Set `length = 1`, `maxLength = 1`.
3. **Next number (`2`)**:
    - `current = 2`
    - `previous = 3`, `current = 2`
    - Since `3 > 2`, not increasing → enter `else` block.
    - `maxLength < length` is false (both are 1), no update.
    - Reset `length = 1` for a new sequence.
4. **Next number (`1`)**:
    - `previous = 2`, `current = 1`
    - `2 > 1`, not increasing → again reset `length = 1`.
5. **Next number (`3`)**:
    - `previous = 1`, `current = 3`
    - `1 < 3`, increasing → extend sequence.
    - `length = 2`
6. **Next number (`5`)**:
    - `previous = 3`, `current = 5`
    - `3 < 5`, increasing → extend sequence.
    - `length = 3`
7. **Next number (`-1`)**:
    - `current = -1`, end of input → exit loop.

---

### **Final Check After Loop**

- At this point:
    - `maxLength = 1`
    - `length = 3` (from sequence `1 → 3 → 5`)
- Final `if` check:
    - `if maxLength < length` → true
    - Update `maxLength = 3`

---

### **Final Output**

- The program prints:
    - **"Maximum length of increasing contiguous subsequence is 3"**