# 🧠 Lecture Notes – Logical Operators and Leap Year Calculation in C

---

## 🔢 Recap: Comparison & Modulo Operators

### 🧮 Modulo Operator (`%`)

- `a % b` → Remainder when `a` is divided by `b`
- Used to test divisibility

#### ✅ Example: Test if number is divisible by 6


```c
int a; scanf("%d", &a);  
if (a % 6 == 0)     
	printf("%d is divisible by 6\n", a); 
else     
	printf("%d is not divisible by 6\n", a);
```

---

## 🔗 Checking Multiple Conditions

### Example: Check if number is divisible by **6 and 4**

```c
int a; scanf("%d", &a);  
if (a % 6 == 0) {     
	if (a % 4 == 0)         
		printf("%d is divisible by 6 and 4\n", a); 
}
```

> 🔍 This is a **nested `if`** structure. Only if `a % 6 == 0`, we check `a % 4 == 0`.

---

## ⚙️ Logical Operators in C

|Operator|Symbol|Meaning|Evaluates To|
|---|---|---|---|
|AND|`&&`|Both conditions must be true|1 (true) or 0 (false)|
|OR|`||`|
|NOT|`!`|Reverses the truth value|1 or 0|

### 🧪 Combined Example (6 and 4):

```c
if ((a % 6 == 0) && (a % 4 == 0))     
	printf("%d is divisible by 6 and 4\n", a);
```

---

## 🔍 Truth Tables

### ✅ AND (`&&`)

|a|b|a && b|
|---|---|---|
|0|0|0|
|0|1|0|
|1|0|0|
|1|1|1|

➡️ If **any** value is `0`, result is `0`

### ✅ OR (`||`)

|a|b|a \| b|
|---|---|---|
|0|0|0|
|0|1|1|
|1|0|1|
|1|1|1|

➡️ If **either** value is non-zero, result is `1`

### ✅ NOT (`!`)

|a|!a|
|---|---|
|0|1|
|1|0|

➡️ **Negates** the condition: true becomes false, and vice versa

---

## 🏎️ Short-Circuit Evaluation

### AND (`&&`):

- If **first condition is false (0)**, second is **not evaluated**

```c
if (a == 0 && b == 10) { 
	... } // b is never checked if a == 0
```

### OR (`||`):

- If **first condition is true (non-zero)**, second is **not evaluated**

```c
if (a != 0 || b == 10) { 
	... } // b is not checked if a != 0
```

---

## 🧠 All Logical Expressions Return `int` (0 or 1)

- Even though `a` and `b` can be of any type (`float`, `int`, etc.), logical expressions always return:
    
    - `0` → false
    - `1` → true
- Example:

```c
printf("%d\n", (a % 6 == 0) && (a % 4 == 0)); // prints 1 or 0
```

---

## 🚫 NOT Operator (`!`)

### Example: Test if a number **is NOT divisible by 3**

```c
if (!(a % 3 == 0))     
	printf("%d is not divisible by 3\n", a);
```

---

## 🧠 Leap Year Logic

### 📅 What is a Leap Year?

A year is a leap year if:
1. Divisible by **4**
2. **Not** divisible by **100**, unless also divisible by **400**

### 🤔 Why This Rule?

- Solar year ≈ **365.242375** days
- We:
    - Add a day every **4 years**
    - Skip leap day **every 100 years**
    - Add it back **every 400 years**

### 🧾 Logical Expression (in C):

```c
if ((year % 4 == 0) && (!(year % 100 == 0) || (year % 400 == 0)))
	printf("%d is a leap year\n", year); 
else     
	printf("%d is not a leap year\n", year);
```

### 🧪 Breakdown:

|Part|Meaning|
|---|---|
|`year % 4 == 0`|Year is divisible by 4|
|`!(year % 100 == 0)`|Not divisible by 100|
|`year % 400 == 0`|Divisible by 400|
|`!(year % 100 == 0)||
|Whole `if` condition|Validates leap year rule as per calendar|

---

### 📌 Example Evaluations

#### ✅ Year = 400:

- Divisible by 4 ✅
- Divisible by 100 ✅
- Divisible by 400 ✅
- → Leap year ✅

#### ❌ Year = 1900:

- Divisible by 4 ✅
- Divisible by 100 ✅
- Not divisible by 400 ❌
- → Not a leap year ❌

#### ✅ Year = 2004:

- Divisible by 4 ✅
- Not divisible by 100 ✅
- → Leap year ✅

---

## ✅ Summary

|Concept|Description|
|---|---|
|Modulo operator `%`|Checks divisibility|
|Logical AND `&&`|True if **both** conditions are true|
|Logical OR `||
|Logical NOT `!`|Reverses truth value|
|Short-circuiting|C stops evaluating if result is determined|
|Leap year rule|4 ✅, 100 ❌ unless also 400 ✅|
|Logical expressions|Return `int` (0 or 1)|