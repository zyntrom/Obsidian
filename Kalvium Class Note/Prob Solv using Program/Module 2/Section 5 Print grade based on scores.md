# 🧠 Control Structures – Print Grade Based on Scores

## 📘 Concept Overview

This program determines a student's grade based on their score using **multi-branch conditional statements**:

- In **Python**: `if-elif-else` ladder
- In **C++**: `if-else-if` ladder

These ladders check one condition at a time, top-down, and execute the first condition that is true.

### 📊 Grading System

|Marks Range|Grade|
|---|---|
|90 – 100|A|
|80 – 89|B|
|70 – 79|C|
|60 – 69|D|
|Below 60|F|
|Invalid input|Retry message|

If the score is not in the 0–100 range, the program should prompt the user to enter a valid score again.

---

## 🧮 Logic Flow (Example Explanation)

Imagine sorting students into rows:

- Ask: Is your score ≥ 90? → If **yes**, Grade A
- Else: Is your score ≥ 80? → If **yes**, Grade B
- ...and so on until all possibilities are covered
- If score < 60 → Grade F
- If score < 0 or > 100 → Invalid input

---

## 🧪 Sample Input/Output

**Input:** 93  
**Output:** Grade A

**Input:** 78  
**Output:** Grade C

**Input:** 45  
**Output:** Grade F

**Input:** -5  
**Output:** Invalid score! Please retry.

---

## 💻 Program (Python)

```python
score = int(input("Enter your score: "))  
if score >= 90 and score <= 100:  
	print("Grade A")  
elif score >= 80 and score <= 89:  
	print("Grade B")  
elif score >= 70 and score <= 79:  
	print("Grade C")  
elif score >= 60 and score <= 69:  
	print("Grade D")  
elif score >= 0 and score < 60:  
	print("Grade F")  
else:  
	print("Invalid score! Please retry.")
```

---
## 💻 Program (C++)

```c++
#include <iostream> 
using namespace std;  
int main() {  
	int score;  
	cout << "Enter your score: ";  
	cin >> score;   
	if (score >= 90 && score <= 100) {   
		cout << "Grade A" << endl;  }  
	else if (score >= 80 && score <= 89) {   
		cout << "Grade B" << endl;  }  
	else if (score >= 70 && score <= 79) {   
		cout << "Grade C" << endl;  }  
	else if (score >= 60 && score <= 69) {   
		cout << "Grade D" << endl;  }  
	else if (score >= 0 && score < 60) {   
		cout << "Grade F" << endl;  }  
	else {   
		cout << "Invalid score! Please retry." << endl;  
	}   
	return 0; 
}
```

---

## 🔍 Explanation of C++ Version

- **cin** is used to get input from the user.
- `if-else if` ladder checks each score range in descending order.
- `&&` ensures both lower and upper bounds are satisfied for each range.
- An **else block** catches invalid scores like negative numbers or those above 100.
- `cout` prints the appropriate grade or error message.
- **return 0** marks the end of the main function.
## 🧠 Key Concepts Used

- Conditional branching (`if-elif-else`)
- Relational operators: `>=`, `<=`, `<`, `>`
- Logical flow based on score ranges
- Input validation