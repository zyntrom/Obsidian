# 🧠 Problem Solving using Programming

## 📌 Topic: Switch-Case Statements

---

## 🧾 What is a Switch Statement?

A **switch** statement allows a program to **choose between multiple fixed options** based on a single variable’s exact value.

- More organized than long chains of `if-else-if`
- Best used when checking **discrete, exact matches** (like menu choices, month numbers, etc.)

---

## 🔄 Structure of a Switch Statement (C++)

**Parts of a switch block:**
1. **switch(variable)** – the variable whose value is checked
2. **case value:** – defines what happens for each possible value
3. **break;** – prevents fall-through
4. **default:** – runs if no case matches (optional but recommended)

---

## 🧩 When to Use?

|Use Case|Preferred Control|
|---|---|
|Multiple specific values|Switch|
|Complex or range-based logic|If-Else|

---

## 🛠️ Example: Month Mapper (C++)

```c++
#include <iostream> 
using namespace std;  
int main() {     
	int month;     
	cout << "Enter month number (1-12): ";     
	cin >> month;      
	switch (month) {         
		case 1: 
			cout << "January" << endl; 
			break;         
		case 2: 
			cout << "February" << endl; 
			break;         
		case 3: 
			cout << "March" << endl; 
			break;         
		case 4: 
			cout << "April" << endl; 
			break;         
		case 5: 
			cout << "May" << endl; 
			break;         
		case 6: 
			cout << "June" << endl; 
			break;         
		case 7: 
			cout << "July" << endl; 
			break;         
		case 8: 
			cout << "August" << endl; 
			break;         
		case 9: 
			cout << "September" << endl; 
			break;         
		case 10: 
			cout << "October" << endl; 
			break;         
		case 11: 
			cout << "November" << endl; 
			break;         
		case 12: 
			cout << "December" << endl; 
			break;         
		default: 
			cout << "Invalid month number!" << endl;     
		}      
	return 0; 
}
```

---

## 🔎 How This Code Works:

- An `int` variable `month` is declared.
- User inputs a value between 1 and 12.
- The `switch` statement compares `month` with each `case`.
- When a match is found:
    - The matching block runs.
    - `break` prevents further cases from running.
- If no case matches, `default` prints an error message.

---

## ⚠️ Important Notes

- **Break is crucial**: Without it, the code may "fall through" and execute the next case(s).
- **No switch in Python**:
    - Use `if-elif-else` or a **dictionary mapping** instead.

---

## ✅ Summary

- The switch-case structure simplifies code that checks for **exact matches**.
- Improves **readability** and **efficiency**.
- Use `default` to handle unexpected input.
- Python does not support `switch` natively but can simulate it.