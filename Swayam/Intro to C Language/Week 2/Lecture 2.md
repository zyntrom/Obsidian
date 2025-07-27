# 🔁 **While Loop in C (Part 2): Summing Input & Loop Invariants**

## ✅ **Goal**

- Continue the earlier program:
    - Read integers until `-1` is entered.
    - Compute and output the **sum** of all values **before** `-1`.

---

## 🧱 **Program Setup**

### 🔢 **Variables**

- `int a` → to store each input number.
- `int s` → to store the **running sum**.

### 🟢 **Important Initialization**

- `s = 0;` → Always initialize before using.
    - Without this, `s` may contain garbage values.
- `a` is read right after declaration, so it need not be initialized manually.

---

## 🔁 **Modified While Loop Logic**

```c
scanf("%d", &a); s = 0;  
while (a != -1) {     
	s = s + a;     
	scanf("%d", &a); 
}  
printf("Sum is %d\n", s);
```

### 🔂 **Explanation**

1. Read the first number into `a`.
2. If `a != -1`, enter the loop.
3. Add `a` to the sum (`s`).
4. Read the next number into `a`.
5. Repeat until `a == -1`.
6. Print the final value of `s`.

---

## 📥 **Example Execution (Tracing Input)**

**Input:** `4 15 -5 -1`

|Step|`a` Value|`s` Before|Action Taken|`s` After|
|---|---|---|---|---|
|1|4|0|s = s + a → 0 + 4|4|
|2|15|4|s = 4 + 15|19|
|3|-5|19|s = 19 + (-5)|14|
|4|-1|-|Loop exits|14|

### 🛑 **Key Point**

- **`-1` is not included** in the sum — it acts as a sentinel (termination signal).

---

## 🔁 **Iterations**

- An **iteration** = one complete execution of the loop body.
- In the above input:
    - Loop iterates 3 times (4, 15, -5).
    - `-1` is **not counted** as an iteration since loop exits **before** it executes.

---

## 🧠 **Loop Invariant**

> A **loop invariant** is a property that holds **true at the beginning of each loop iteration.**

### 🧩 **Invariant in This Program**

- `s` always holds the **sum of all values read so far, _excluding_ the current value in `a`**.

#### 📌 Step-by-step:

- Before loop starts: `s = 0`, `a = first input`.
- In loop:
    - Add current `a` to `s`.
    - Read new value into `a`.
- So, at **start of next iteration**, `s` has sum of all previous values, and `a` is the next input.

### ✅ **Why Invariants Matter**

- If the loop invariant is true throughout and loop **terminates correctly**, then:
    - The **final value of `s` is guaranteed** to be the correct sum.
    - In our case: since loop stops on `-1` and invariant excludes current `a`, `-1` is not summed.

---

## 📚 **Terminology Recap**

|Term|Meaning|
|---|---|
|**Sentinel Value**|Special value that indicates end of input (here: `-1`)|
|**Loop Iteration**|One full cycle of reading → summing → reading again|
|**Loop Invariant**|A property or condition that is always true at the **start** of loop|
|**Initialization**|Setting a variable to a known value before use (e.g., `s = 0`)|

---

## ✅ **Takeaway**

- Use **loop invariants** to reason about and verify the correctness of loops.
- Always **initialize accumulators** like sums or counters.
- Design loops with care to handle **termination conditions** and **edge cases** like sentinel values.