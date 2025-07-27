## 🔁 **Infinite Loops and Exiting Loops in C**

### 📌 **What is an Infinite Loop?**

- A **loop that never terminates** unless forcefully interrupted.
- **Most basic form**: `while(1)`
    - `1` is always **true** in C.
    - So `while(1)` means the loop runs **forever**.

### 🖼️ **Example of Infinite Loop**

```c
while (1)     
	printf("Hi! I am an infinite loop.\n");
```

- This prints the message **forever**.
- To **exit manually** (e.g., in Linux): press **Ctrl+C**.

---

## ⛔ **Exiting Loops – `break` Statement**

### ✅ **Purpose**

- The `break` statement is used to **exit the innermost loop** immediately.
- Applicable to all loop types (`while`, `for`, `do-while`) and `switch`.

---

### 🧮 **Example: Summing Numbers Until -1 is Seen**

```c
int a, sum = 0; 
while (1) {     
	scanf("%d", &a);     
	if (a == -1)         
		break;     
	sum += a; 
} 
printf("Sum = %d", sum);
```

#### 🧾 Sample Input:

```
5 3 2 -1
```

#### ✅ Execution Flow:

- `5` → added to `sum` → sum = 5
- `3` → added → sum = 8
- `2` → added → sum = 10
- `-1` → triggers `break` → loop ends
- Output: `Sum = 10`

> 💡 `break` exits only the **innermost loop**, not just the `if`.

---

## 🧑‍💻 **Using `break` in Text Input Example (Mini Editor)**

### 🖋️ **Problem Setup**

- Build a **simple text editor** simulation.
- User can enter text up to **maximum characters** (e.g., 1000).
- **Two ways to stop**:
    1. Maximum character limit reached.
    2. A **blank line** (two consecutive newline characters).

---

### 🧱 **Approach Using `break`**

- Use `getchar()` or `scanf("%c")` to read characters one by one.
- Track:
    - `current` character
    - `previous` character

#### 🔁 Loop using `for`:

```c
for (i = 0; i < max_chars; i++) {     
	previous = current;     
	current = getchar();     
	if (current == '\n' && previous == '\n')         
		break; 
}
```

- `break` occurs if a **blank line** is entered.

---

## 🏳️ **Avoiding `break` with Flag Variables**

### 🔁 **Alternative Style (No `break`)**

- Use a `flag` variable to indicate when a special condition occurs.

#### ✅ Example:

```c
int flag = 0; 
for (i = 0; i < max_chars && flag == 0; i++) {     
	previous = current;     
	current = getchar();     
	if (current == '\n' && previous == '\n')         
		flag = 1; 
}
```

### ⚖️ **Pros and Cons**

|Using `break`|Using `flag`|
|---|---|
|Simpler in some situations|Slightly more verbose|
|Exit condition **inside** loop|Exit condition is **clearly visible** in loop header|
|Can make code harder to read|Often easier to maintain and debug|

> 🧠 **Key point**: Choose based on readability, complexity, and preference.

---

## ⚠️ **Important Behavior of `break` in `for` Loops**

### 🚦 Normal `for` loop execution order:

1. **Initialization**
2. **Test**
3. **Body execution**
4. **Update**
5. Repeat from step 2

### ❗ `break` skips the update

- When `break` is encountered:
    - The **loop exits immediately**
    - **Update step is skipped**

#### 🧪 Example:

```c
for (i = 0; i < 10; i++) {     
	if (i % 2 == 1)         
		break; 
} 
printf("%d\n", i);
```

- `i = 0` → no break
- `i = 1` → `1 % 2 == 1` → break
- `printf` prints **1**, not 2

> Because `i++` is **not executed** after break.

---

## 🔚 **Summary**

- `while(1)` creates infinite loops; useful for indefinite input.
- `break` exits **innermost loop**, even if nested.
- You can **simulate break** using `flag` variables and structured conditions.
- Be aware that `break` **bypasses** the loop's update step.
- Prefer `for` loops when number of iterations is **known**, e.g., reading `n` items.
- Use style (`break` vs. `flag`) that offers **clearer logic and readability** in your context.