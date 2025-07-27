# 🌀 **Loops in C Programming: While Loop**

## ✅ **Introduction to Loops**

- Loops are used to **repeat a set of statements** based on a condition.
- They are fundamental to programming.
- Unlike flowcharts (where loop-back arrows were used), programming languages provide **explicit loop constructs**.

---

## 🔄 **Syntax of `while` Loop**

```c
while (expression)     
	statement;
```

- **Expression**: Condition to check before every loop iteration.
- **Statement**: Executed **only if** the expression evaluates to true (non-zero in C).

---

## 📊 **Flowchart of `while` Loop**

1. Evaluate expression:
    - If **true**, execute statement.
    - After execution, go back and evaluate expression again.
    - If **false**, exit loop and continue with code after the loop.

---

## 📌 **Key Points**

- A `while` loop is similar to an `if` block **without `else`**, but with **repetition**.
- Condition is checked **before** each iteration.
- Loop runs as long as condition is **true**.
- It exits **immediately** when condition becomes false.

---

## 🔁 **Extended Form**

```c
while (expression) {     
	statement1; 
} 
statement2;
```

- If the expression is true:
    - `statement1` is executed repeatedly.
- If the expression is false:
    - Control moves directly to `statement2`.

---

## 🧠 **Conceptual Difference with `if`**

- In `if`, once `statement1` is executed (when condition is true), control **moves on**.
- In `while`, after executing `statement1`, it **loops back** and checks condition again.

---

## 🧪 **Example Problem**

**Problem**:  
Read a sequence of integers from user until `-1` is entered.  
Sum all the numbers and print the total.  
`-1` is the sentinel value (marks end of input).

---

## 🛠️ **Approach**

1. Use `scanf()` to read an integer.
2. Use `while (a != -1)` to check whether to continue.
3. Inside loop:
    - Add number to sum.
    - Read next number.
4. When `-1` is entered, exit loop and print sum.

---

## 📥 **Input Trace Example**

- Input: `4 15 -5 -1`
- Execution:
    - a = 4 → not -1 → loop → read 15
    - a = 15 → not -1 → loop → read -5
    - a = -5 → not -1 → loop → read -1
    - a = -1 → loop exits

---

## 🧾 **Important Notes**

- The condition `a != -1` is **tested at the start** of each iteration.
- If the very first number is `-1`, the loop is **not entered at all**.
- Used for problems where you **don't know how many inputs** will be provided.

---

## 💡 **Common Use Cases of While Loops**

- Reading unknown number of inputs
- Waiting for a condition to become false (e.g., file end, sensor input)
- Menu-driven programs (loop until exit is selected)

---

## 📚 **Keywords & Concepts**

|Term|Meaning|
|---|---|
|Sentinel value|Special input to indicate termination (here, -1)|
|Expression|Condition checked before each iteration|
|Loop control|Determines when loop enters and exits|
|Pre-check loop|Loop that checks condition _before_ running|