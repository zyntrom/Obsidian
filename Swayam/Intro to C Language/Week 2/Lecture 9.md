## 🧭 **For Loop in C**

### 🔹 **Overview**

- **For loop** is one of the most popular looping constructs in C.
- **While** and **do-while** loops are available but `for` is preferred in most real-world C programs.
- The `for` loop is slightly more complex syntactically than the `while` loop but is **intuitive** once you get used to it.

---

## 🔧 **Syntax of `for` Loop**

```c
for (initialization; test condition; update) {     
	// loop body 
}
```

### ▶️ **Execution Flow**

1. Execute **initialization** (only once).
2. Check **test condition**.
    - If true → enter loop.
    - If false → exit loop.
3. Execute the **loop body** (statement).
4. Execute **update** expression.
5. Go back to step 2.

---

## 🔁 **Equivalent `while` Loop**

Any `for` loop can be rewritten as a `while` loop:

```c
initialization; 
while (test condition) {     
	statement;     
	update; 
}
```

> ✅ They're nearly equivalent **unless control statements like `break` or `continue` are involved** (to be discussed later).

---

## 📌 **Key Parts Mapping**

- **Initialization** → First part of `for` loop
- **Test condition** → Second part
- **Update expression** → Third part (executed after each loop iteration)
- **Important**: Update happens **after** the loop body execution.

---

## 🧪 **Example 1: Sum of Reciprocals from 1 to 100**

![[Pasted image 20250728001122.png]]
### 🔣 Variables:

- `float reciprocal_sum = 0;`
- `int i;`

### 🔁 Loop Structure:

```c
for (i = 1; i <= 100; i++) {     reciprocal_sum += 1.0 / i; }
```

### 🔍 Dry Run (from 1 to 4):

- i = 1 → sum = 0 + 1 = 1.0
- i = 2 → sum = 1.0 + 0.5 = 1.5
- i = 3 → sum = 1.5 + 0.333 = 1.833
- i = 4 → sum = 1.833 + 0.25 = 2.083
- i = 5 → test fails (`5 > 4`) → loop ends

---

## 🧪 **Example 2: Sum of `m` Numbers**

### ✏️ Problem:

- First line: `m` (number of integers to sum)
- Second line: `m` integers  
    ➡️ Output the sum of those `m` integers

### 🔣 Variables:

```c
int m, i, sum = 0, num;
```

### 🔁 Loop Structure:

```c
scanf("%d", &m); 
sum = 0; 
for (i = 0; i < m; i++) {     
	scanf("%d", &num);     
	sum += num; 
}
```

> ✅ In C, it's **more common** to loop from `i = 0` to `i < m`.

---

## ✅ **Advantages of `for` loop over `while` loop**

1. **Clarity**: Initialization, test, and update are on a single line → easy to read.
2. **Compactness**: Requires fewer lines of code.
3. **Preferred by C programmers** for clarity and style.

---

## 💡 **Syntactic Shortcut: Comma Operator**

You can initialize multiple variables in one statement using the **comma operator**:

```c
for (sum = 0, i = 0; i < m; i++) {     
	// loop body 
}
```

- Executes left to right
- Helps keep initialization clean and compact

---

## 📝 **Practice Recommendation**

- Rewrite a `for` loop using a `while` loop, and vice versa.
- Understand how both can model the same logic but with different structure.