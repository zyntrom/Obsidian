# 🧠 Problem Solving using Programming

## 📌 Topic: FizzBuzz Challenge

---

## 📝 What is FizzBuzz?

FizzBuzz is a classic beginner-level programming challenge used to teach **control structures**, especially conditionals.

### 🔹 Problem Statement:

- If a number is divisible by 3 → print `"Fizz"`
- If a number is divisible by 5 → print `"Buzz"`
- If a number is divisible by both 3 and 5 → print `"FizzBuzz"`
- If it's divisible by neither → print `-1`

---

## ⚙️ Step-by-Step Learning

### ✅ Step 1: Checking Divisibility

- Use the **modulo operator `%`** to check for divisibility.
- Syntax:
    - `number % 3 == 0` means number is divisible by 3
    - Example:
        - 9 % 3 = 0 → ✅ divisible
        - 10 % 3 = 1 → ❌ not divisible

---

### ✅ Step 2: Handling Multiple Specific Conditions

- Use **if**, **else if / elif**, and **else** to check:
    - First: divisible by **both 3 and 5**
    - Then: only 3
    - Then: only 5
    - Else: not divisible by either
- Use logical **AND** operator (`&&` in C++, `and` in Python) to check for both conditions.

---

### ✅ Step 3: Order of Conditions Matters

- Always check **most specific condition first**:
    - Check `number % 3 == 0 and number % 5 == 0` **before** other cases.
- Why?
    
    - Because `number % 3 == 0` will be `true` even for 15, but we want to catch that as `"FizzBuzz"`, not just `"Fizz"`.

---

## 🔄 Final Logic Summary:

1. If divisible by 3 and 5 → print "FizzBuzz"
2. Else if divisible by 3 → print "Fizz"
3. Else if divisible by 5 → print "Buzz"
4. Else → print -1

---

# 🧪 Example Programs

---

## 🔸 Python

```python
number = int(input("Enter a number: "))  
if number % 3 == 0 and number % 5 == 0:     
	print("FizzBuzz") 
elif number % 3 == 0:     
	print("Fizz") 
elif number % 5 == 0:     
	print("Buzz") 
else:     
	print("-1")
```

---

## 🔹 C++

```c++
#include <iostream> 
using namespace std;  
int main() {     
	int number;     
	cout << "Enter a number: ";     
	cin >> number;      
	if (number % 3 == 0 && number % 5 == 0)         
		cout << "FizzBuzz" << endl;     
	else if (number % 3 == 0)         
		cout << "Fizz" << endl;     
	else if (number % 5 == 0)         
		cout << "Buzz" << endl;     
	else         
		cout << "-1" << endl;      
	return 0; 
}
```

---

## 🧠 Key Concepts Covered:

- Modulo operator `%` for divisibility
- if-elif-else (or if-else-if) structure
- Logical AND condition checking
- Prioritizing checks in conditional branching

---

## 📚 Application:

FizzBuzz teaches foundational concepts in **branching logic**, **modulo usage**, and **prioritizing conditions** — important for real-world coding and technical interviews.