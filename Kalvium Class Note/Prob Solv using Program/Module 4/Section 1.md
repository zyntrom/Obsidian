# 📘 Notes: Modularity with Functions (Kalvium 4.1)

---

## 🌟 Introduction

- In the previous challenge, we controlled a **Mars Lander** using code.
- Now, the focus shifts to **modularity in programming**.
- Just like spaceships are built from **modules**, programs can also be built from smaller building blocks.
- **Functions** are the building blocks that help in modular programming.
    

---

## 🎯 Learning Objectives

By the end of this lesson, you should be able to:

1. Understand **what modularity is** and why it’s important.
    
2. Learn how **functions act as building blocks** for modular code.
    
3. Decompose a **problem into smaller tasks**, each handled by a function.
    
4. Apply this modular approach to coding problems presented as **function requirements**.
    
5. Implement a program that **checks if a number is divisible by the sum of its digits using functions**.
    

---

## 🏗️ Embracing Modularity in Programming

- Modularity = **Dividing a program into independent modules**.
    
- Each module:
    
    - Performs a **specific task**.
        
    - Can be **developed, tested, and maintained independently**.
        
- Advantages:
    
    - Easier to **understand**.
        
    - Easier to **debug** (fix errors).
        
    - Easier to **reuse**.
        
- Analogy:
    
    - Building a **house**: foundation, framing, plumbing → all separate but combine to make the house.
        
    - Similarly, in code → each function/module = one job.
        

---

## 🔧 Functions: The Building Blocks

- **Definition:** Functions are **self-contained blocks of code** that perform a specific task.
    
- **Inputs (Arguments):** Data provided to the function.
    
- **Output (Return value):** Result produced by the function.
    
- Functions **encapsulate complexity** → hide details inside the function.
    
- Benefits:
    
    - Code becomes **cleaner and organized**.
        
    - Code becomes **reusable**.
        
    - Acts like **documentation** if named properly.
        

### 📌 Example: Python

`def add(x, y):     return x + y  result = add(5, 3) print(result)  # Output: 8`

### 📌 Example: C++

`#include <iostream> using namespace std;  int add(int x, int y) {     return x + y; }  int main() {     int result = add(5, 3);     cout << result; // Output: 8     return 0; }`

---

## 🔍 Decomposing Problems into Functional Tasks

- **Process:**
    
    1. Identify the distinct steps in a task.
        
    2. Assign each step to a separate function.
        
    3. Each function has **input → operation → output**.
        
    4. Main program **orchestrates function calls**.
        

### Example: Area of a Rectangle

Steps:

1. Get length.
    
2. Get width.
    
3. Multiply → area.
    

#### Python

`def get_length():     return int(input("Enter length: "))  def get_width():     return int(input("Enter width: "))  def calculate_area(length, width):     return length * width  length = get_length() width = get_width() area = calculate_area(length, width) print("Area:", area)`

#### C++

`#include <iostream> using namespace std;  int get_length() {     int length;     cin >> length;     return length; }  int get_width() {     int width;     cin >> width;     return width; }  int calculate_area(int length, int width) {     return length * width; }  int main() {     int length = get_length();     int width = get_width();     int area = calculate_area(length, width);     cout << "Area: " << area << endl;     return 0; }`

---

## 💻 Solving Problems with Function Requirements

- In coding platforms, problems are often given as **function requirements**:
    
    - Function must take **specific input parameters**.
        
    - Function must return **specific output**.
        
- **Steps:**
    
    1. Understand input & output data types.
        
    2. Break problem into smaller tasks.
        
    3. Implement inside functions.
        

### Example: Factorial

#### Python

`def factorial(n):     if n == 0:         return 1     return n * factorial(n-1)`

#### C++

`int factorial(int n) {     if (n == 0) return 1;     return n * factorial(n-1); }`

---

## 🧩 Coding Challenge: Divisible by Sum of Digits

**Problem Statement:**  
Write a program that takes an integer as input and checks if it is divisible by the sum of its digits.

**Requirements:**

1. `sum_of_digits(n)` → returns the sum of digits of n.
    
2. `is_divisible(n)` → checks if n is divisible by sum of its digits.
    

---

### ✅ Python Solution

`def sum_of_digits(n):     total = 0     while n > 0:         total += n % 10  # get last digit         n //= 10         # remove last digit     return total  def is_divisible(n):     return n % sum_of_digits(n) == 0  # Main Program num = int(input("Enter a number: ")) if is_divisible(num):     print(num, "is divisible by the sum of its digits.") else:     print(num, "is not divisible by the sum of its digits.")`

#### 🔎 Explanation (Python)

1. `sum_of_digits(n)`:
    
    - Uses `% 10` to extract last digit.
        
    - Adds digit to total.
        
    - Uses `// 10` to remove last digit.
        
    - Repeats until n becomes 0.
        
2. `is_divisible(n)`:
    
    - Gets sum of digits using `sum_of_digits`.
        
    - Checks if `n % sum == 0`.
        
3. Main program:
    
    - Takes input.
        
    - Calls function.
        
    - Prints result.
        

---

### ✅ C++ Solution

`#include <iostream> using namespace std;  int sum_of_digits(int n) {     int total = 0;     while (n > 0) {         total += n % 10; // last digit         n /= 10;         // remove last digit     }     return total; }  bool is_divisible(int n) {     return n % sum_of_digits(n) == 0; }  int main() {     int num;     cout << "Enter a number: ";     cin >> num;      if (is_divisible(num))         cout << num << " is divisible by the sum of its digits." << endl;     else         cout << num << " is not divisible by the sum of its digits." << endl;      return 0; }`

#### 🔎 Explanation (C++)

- **sum_of_digits**:
    
    - `% 10` extracts last digit.
        
    - `n /= 10` removes last digit.
        
    - Keeps adding digits until n becomes 0.
        
- **is_divisible**:
    
    - Checks if remainder is 0 when dividing n by sum of its digits.
        
- **main**:
    
    - Reads number.
        
    - Calls function.
        
    - Prints result.
        

---

## 📌 Summary

- **Modularity = breaking problems into smaller modules (functions).**
    
- **Functions = building blocks of modularity** → reusable, testable, organized.
    
- We learned:
    
    - How to decompose problems.
        
    - How to implement function-based solutions.
        
    - How coding platforms use function requirements.
        
- **Hands-on challenge** (divisible by sum of digits) demonstrated modular design.