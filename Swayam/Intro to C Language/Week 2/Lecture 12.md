## 🔁 `continue` Statement in C

### 📌 Purpose:

- Used **inside loops** (`for`, `while`, `do-while`) to **skip the current iteration** and **move to the next one**.
- **Unlike `break`**, it does **not exit** the loop.
- It **skips the rest of the code** inside the current loop body and **proceeds with the next iteration**.

---

## 🆚 `break` vs `continue`

|`break`|`continue`|
|---|---|
|Exits the **innermost loop** immediately.|Skips the **current iteration** and goes to the next one.|
|Used when you're **done with the loop**.|Used when you're **done with this iteration**.|
|Skips all remaining code and update logic.|Skips remaining loop body but **does the update step** in `for` loops.|

---

## 🧠 Use Case: Skipping Negative Numbers

### 💬 Problem:

- Read integers from input stream.
- **Skip negative numbers**.
- **Stop reading** when a **non-digit** (e.g., `.`) is encountered.
- **Find the maximum** among all **positive integers**.

---

### 🧪 Sample Input:

```
1 -1 2 .
```

---

### 🧱 Code Flow Breakdown

1. **Read input** using `scanf("%d", &a)`
    - `scanf` returns **1** if input is a valid integer.
    - Stops when input is not an integer (e.g., `.`).
2. **Check if number is negative**
    - If **negative**, use `continue` → skip to next iteration.
3. **Update max** if current number is greater than max.

---

### 🧮 Example Using `continue`

```c
int a, max = 0; 
while (scanf("%d", &a) == 1) {     
	if (a < 0)         
		continue; // Skip negative numbers     
	if (a > max)         
		max = a; 
} 
printf("Max = %d", max);
```

---

## 🧠 `scanf` Return Value

- `scanf` returns the **number of successful inputs read**.
- In `scanf("%d", &a)`:
    - Returns **1** if an integer is read.
    - Returns **0** if input is not a number (like `.`).
- This allows you to use:
```c
while (scanf("%d", &a) == 1)
```
    to **keep reading until invalid input** (like `.`) is encountered.

---

## ✅ Alternative to `continue`: Nested `if`

### 🧱 Without `continue`:

```c
int a, max = 0; 
while (scanf("%d", &a) == 1) {     
	if (a >= 0) {         
		if (a > max)             
			max = a;     
	} 
}
```

- **Same logic**, but uses extra nesting.
- **No `continue`** used.

> 🧠 These two styles are functionally equivalent.  
> `continue` helps **reduce nesting** and improve **readability**.

---

## 🔄 Behavior of `continue` in Loops

### 🔁 In `while` loops:

- `continue` skips to the **test condition** of the loop.
- Next iteration begins **after test re-evaluation**.

### 🔁 In `for` loops:

Structure:

```c
for (initialization; condition; update) {     
	// loop body 
}
```

- If `continue` is hit:
    - **Skips remaining code in loop body**.
    - **Executes the update expression**.
    - Then, **tests condition** again.
- So, `continue` → goes to **update → condition check → next iteration**.

---

### 🔥 Difference Between `break` and `continue` in `for` Loops:

|Behavior|`break`|`continue`|
|---|---|---|
|Skips update step?|✅ Yes|❌ No (update runs)|
|Exits loop?|✅ Yes|❌ No|
|Next iteration?|❌ No|✅ Yes|

---

## 🧩 Summary

- `continue` is used when **you want to skip rest of the current iteration** and move on.
- **Does not exit** the loop like `break`.
- Especially useful when:
    - You have **many conditions** in a loop.
    - You want to **avoid deep nesting** with `if` statements.
- **Not strictly necessary** – everything can be written using only `if` and logic.
- Makes code **cleaner and easier to read** in some situations.