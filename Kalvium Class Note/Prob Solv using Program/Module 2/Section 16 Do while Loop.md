# 🔁 Do-While Loop (C++)

## 📌 Definition

A `do-while` loop is a control structure that **executes a block of code at least once**, and then continues based on a condition.

> ✅ _Unlike the `while` loop, it checks the condition **after** running the loop body._

---

## 🔍 Key Features

|Feature|Description|
|---|---|
|✅ Guaranteed Execution|The loop body **executes at least once**, even if the condition is false|
|🔁 Condition After|Condition is checked **after** the code runs|
|🧪 Good For|Retrying, menus, user input, simulations, etc.|

---

## 🧪 Syntax (C++)

```c++
do {     
	// Code to run 
} while (condition);
```

- Code inside the `do` block runs first.
- Then the `condition` is checked.
- If `true`, it repeats. If `false`, it stops.

---

## 🧾 Example: Count from 0 to 4

```c++
#include <iostream> 
using namespace std;  
int main() {     
	int count = 0;     
	do {         
		cout << "Count: " << count << endl;         
		count++;     
	} while (count < 5);     
	return 0; 
}
```

### 🔎 Output:

```
Count: 0  Count: 1  Count: 2  Count: 3  Count: 4
```

---

## 🧠 When to Use a Do-While Loop?

- When you want the loop to run **at least once**.
- When the **condition depends on the result of running** the code.
- Examples:
    - Menu systems
    - Input validation (ask again if invalid)
    - Retry mechanisms (like re-attempting network connection)

---

## 🐍 Python Equivalent (No Native Do-While)

Use `while True` with a `break` condition.

```python
while True:     # do something     
	if condition_to_stop:         
	break
```

✅ This simulates the same behavior as a C++ `do-while`.

---

## 🎯 Fun Practice Ideas

1. **User Prompt Loop**  
    Ask the user: "Do you want to continue? (yes/no)"  
    Keep looping until user enters "no".
2. **Temperature Simulator**  
    Print "Still heating..." until temperature reaches 100°C.