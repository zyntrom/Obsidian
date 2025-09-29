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
```embed
title: "Flowchart to check given number is armstrong or not? | #algorithm  & #flowchart #armstrongnumber"
image: "https://i.ytimg.com/vi/gxeM27JTf24/maxresdefault.jpg?sqp=-oaymwEmCIAKENAF8quKqQMa8AEB-AH-CYAC0AWKAgwIABABGFogYihlMA8=&rs=AOn4CLCaYtCm5Q2DFGIyyZlXRmVxOkWraQ"
description: "In this video we are going to discuss about armstrong number, what is armstrong number, algorithm and flowchart to check given number is armstrong or not...I..."
url: "https://youtu.be/gxeM27JTf24"
favicon: ""
aspectRatio: "56.25"
```

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
		n /= 10;     
	}      
	if (sum == num)         
		cout << "Armstrong number" << endl;     
	else         
		cout << "Not an Armstrong number" << endl;      
	return 0; 
}
```

---

### ✅ Python Solution

```python
num = int(input("Enter a number: "))

# Step 1: Count digits
temp = num
digits = 0
while temp > 0:
    digits += 1
    temp //= 10

# Step 2: Calculate Armstrong sum
temp = num
sum_val = 0
while temp > 0:
    digit = temp % 10
    sum_val += digit ** digits
    temp //= 10

# Step 3: Compare
if sum_val == num:
    print("Armstrong number")
else:
    print("Not an Armstrong number")

```

---

### ✅ Java Solution

```java
import java.util.Scanner;

public class Armstrong {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int num = sc.nextInt();
        sc.close();
        int temp = num, sum = 0, digits = 0;
        // Count digits
        int n = num;
        while (n > 0) {
            digits++;
            n /= 10;
        }
        // Calculate Armstrong sum
        n = num;
        while (n > 0) {
            int digit = n % 10;
            sum += Math.pow(digit, digits);
            n /= 10;
        }
        if (sum == num)
            System.out.println("Armstrong number");
        else
            System.out.println("Not an Armstrong number");
    }
}

```