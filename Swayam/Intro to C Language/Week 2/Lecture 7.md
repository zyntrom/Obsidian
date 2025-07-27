## 🔁 **Looping in C: Introducing the `do-while` Loop**

### 🔹 What is a `do-while` Loop?

- A `do-while` loop is an **alternative looping mechanism** in C.
- It is a **variant of the `while` loop**.
- **Syntax**:
```c
do {     
	statement; 
} while (expression);
```
    
- **Important syntax difference**:
    - The `do-while` loop **ends with a semicolon (;)**.
    - The `while` loop **does not require a semicolon** after the condition block.

---

### 🔄 **Execution Flow of `do-while` Loop**

1. Execute the **statement block first**.
2. Then test the **condition (expression)**.
3. If condition is `true`, **go back to step 1**.
4. If condition is `false`, **exit** the loop.

**Key difference**:

- In `do-while`, the loop **executes at least once**, even **before checking** the condition.
- In `while`, the condition is **checked first**, and then the statement is executed **only if the condition is true**.

---

## 🔁 **`while` vs `do-while`: Practical Example**

### 📌 Problem Statement:

> Read and print a sequence of integers **until -1 is seen**, and also **print -1**.

### ✅ Using `while` Loop:

- Declare a variable.
- Scan value.
- If value is `-1`, exit.
- Else:
    - Print the value.
    - Keep scanning inside the loop.
- After loop ends, print `-1`.

> Note: Needs **extra scanf before loop** and **extra printf after loop**.

---

### ✅ Using `do-while` Loop:

- Declare and scan variable.
- **Always print the scanned value** (even if it’s `-1`).
- Then check if value is `-1`:
    - If yes, **exit** the loop.
    - If no, **go back to scan next number** and continue.

> Advantage: More elegant and shorter.  
> Avoids pre-scan and post-print logic.

---

## 💡 Expressiveness of Loops

- `while` and `do-while` are **equally powerful**.
- No program is **impossible** to write in one but possible in the other.
- However, some problems are **easier or shorter** to implement using `do-while`.

---

## ⚠️ Common Error in `do-while`

- **Missing semicolon (`;`)** after the `while(condition)` line.
- This is a **common syntax error**, especially for beginners.

---

## 🧠 Tip for Beginners

- Stick to **one loop type** (e.g., always use `while`) when learning.
- Once you're **comfortable**, switching between them becomes easy.

---

## 🧪 Problem: Length of Longest Contiguous Increasing Subsequence (Ending in -1)

### 📝 Goal:

> Modify previous logic to **include -1** in the sequence.

### 🧱 Old Logic (Using `while`):

- Did **not include -1** in the calculation.
- Checked for `-1` **before** processing the number.

---

### 🔁 New Logic (Using `do-while`):

#### 🧮 Initialization:

- Start with necessary counters (e.g., `length`, `max_length`).
- Read first number (`current`), and set `previous`.

#### 🔁 Loop:

1. Compare `current` with `previous`:
    - If `current > previous`, **extend the sequence**.
    - Else, **start a new sequence** with `length = 1`.
2. Update `previous` to `current`.
3. Read next number into `current`.
4. At end of loop, check if `current == -1`:
    - If yes, **exit**.
5. After loop, update `max_length` if needed.

---

### ✅ Benefit of `do-while` Here:

- Automatically processes `-1` **before checking** the condition.
- So `-1` is also **included** in the increasing sequence calculation.

---

## ✅ Summary

|Feature|`while` Loop|`do-while` Loop|
|---|---|---|
|Condition checked|Before executing the loop body|After executing the loop body|
|Executes at least once|No|Yes|
|Syntax ends with `;`|No|**Yes**|
|Common beginner mistake|Not applicable|**Forgetting the semicolon (;)**|
|Suitable when|You may not want to run loop initially|You want to run loop at least once|