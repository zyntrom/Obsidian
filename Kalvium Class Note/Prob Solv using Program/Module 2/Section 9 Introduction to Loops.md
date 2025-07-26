## 📘 SPE 2025 – Control Structures: Loops (Introduction)

### 🔁 What is a Loop?

- A **loop** is a control structure that **repeats a block of code** multiple times.
- The repetition continues:
    - For a **fixed number** of times (e.g., counting)
    - While a **condition** is true (e.g., waiting for input)
- **Purpose**: Avoid manual repetition, make code cleaner and more efficient.

---

## 🔢 The `for` Loop – Best for Counting

### ✅ Use When:

- You **know exactly** how many times to run.

### 💡 Example:

**Print numbers from 1 to 5**

**Python**

```python
for i in range(1, 6):     print(i)
```

**C++**

```c++
#include <iostream> 
using namespace std;  
int main() {     
	for (int i = 1; i <= 5; i++) {         
		cout << i << endl;     
	}     
	return 0; 
}
```

- Starts at 1
- Ends at 5 (inclusive)
- Increments by 1 each time

---

## 🔄 The `while` Loop – Condition-Based Repetition

### ✅ Use When:

- You **don’t know** the number of repetitions.
- Loop continues as long as a **condition is true**.

### 💡 Example:

**Print numbers from 1 to 5**

**Python**

```
i = 1 while i <= 5:     print(i)     i += 1
```

**C++**

cpp

CopyEdit

`#include <iostream> using namespace std;  int main() {     int i = 1;     while (i <= 5) {         cout << i << endl;         i++;     }     return 0; }`

---

## 🔁 The `do-while` Loop – Run At Least Once (C++ Only)

### ✅ Use When:

- You want the block to run **at least once**, even if the condition is false initially.
    

### 💡 Example:

**Guessing Game**

**C++**

cpp

CopyEdit

`#include <iostream> using namespace std;  int main() {     int guess;     do {         cout << "Guess the number: ";         cin >> guess;     } while (guess != 7);     return 0; }`

- Runs once before checking `guess != 7`
    
- Continues until guess is correct
    

⚠️ **Python Note**: No built-in `do-while` loop. You can use:

python

CopyEdit

`while True:     guess = int(input("Guess the number: "))     if guess == 7:         break`

---

## 🔍 Loop Types Comparison

|Loop Type|Best For|Runs At Least Once|Example Use Case|
|---|---|---|---|
|`for`|Known number of repetitions|❌|Counting, printing tables|
|`while`|Condition-based|❌|User input, waiting for event|
|`do-while`|Guaranteed one execution|✅|Menus, guessing games (C++ only)|

---

## 🧠 Summary

- Loops are powerful tools to **automate repetition**.
    
- Choose the right loop type based on:
    
    - Whether you know the count (`for`)
        
    - Need to check conditions (`while`)
        
    - Must run at least once (`do-while`)