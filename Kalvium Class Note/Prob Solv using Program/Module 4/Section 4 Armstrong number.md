# 📘 Notes: Armstrong Number

## Definition

- An **Armstrong number** (also called **Narcissistic number**) is a number that is equal to the **sum of its digits each raised to the power of the number of digits**.

Example:

- 153 → 1³ + 5³ + 3³ = 153 → Armstrong number
- 9474 → 9⁴ + 4⁴ + 7⁴ + 4⁴ = 9474 → Armstrong number

---

## Steps to Solve

1. **Input Handling** → Read the number `n`.
2. **Count Digits** → Find how many digits the number has. (can use `len(str(n))` in Python or loop in C++/Java).
3. **Digit Processing** → For each digit:
    - Raise it to the power of the total digit count.
    - Add to a running sum.
4. **Comparison** → Check if the sum equals the original number.
    - If yes → Armstrong number.
    - Else → Not an Armstrong number.

---

## Example Walkthrough

Input: `371`
- Step 1: Digits = 3
- Step 2: Calculate →  
    3³ + 7³ + 1³ = 27 + 343 + 1 = 371
- Step 3: Compare → 371 == 371 → Armstrong number ✅

Input: `123`

- Step 1: Digits = 3
- Step 2: Calculate →  
    1³ + 2³ + 3³ = 1 + 8 + 27 = 36
- Step 3: Compare → 36 ≠ 123 → Not Armstrong ❌

---

# 📝 Explanation in Simple Words

- Break the number into digits.
- Count how many digits there are.
- Raise each digit to that power and sum them.
- If the sum matches the original number, it’s an Armstrong number.
- Otherwise, it’s not.

---

# 💻 Solutions

### ✅ C++ Solution

```cpp
#include <iostream> 
#include <cmath> 
using namespace std;  
int main() {     
	int num, temp, sum = 0, digits = 0;     
	cin >> num;     
	temp = num;      // Count digits     
	int n = num;     
	while (n > 0) {         
		digits++;         
		n /= 10;     
	}      
	// Calculate Armstrong sum     
	n = num;     
	while (n > 0) {         
		int digit = n % 10;         
		sum += pow(digit, digits);         
		n /= 10;     }      if (sum == num)         cout << "Armstrong number" << endl;     else         cout << "Not an Armstrong number" << endl;      return 0; }
```

---

### ✅ Python Solution

`num = int(input()) digits = len(str(num)) sum_val = sum(int(digit) ** digits for digit in str(num))  if sum_val == num:     print("Armstrong number") else:     print("Not an Armstrong number")`

---

### ✅ Java Solution

`import java.util.Scanner;  public class Armstrong {     public static void main(String[] args) {         Scanner sc = new Scanner(System.in);         int num = sc.nextInt();         sc.close();          int temp = num, sum = 0, digits = 0;          // Count digits         int n = num;         while (n > 0) {             digits++;             n /= 10;         }          // Calculate Armstrong sum         n = num;         while (n > 0) {             int digit = n % 10;             sum += Math.pow(digit, digits);             n /= 10;         }          if (sum == num)             System.out.println("Armstrong number");         else             System.out.println("Not an Armstrong number");     } }`