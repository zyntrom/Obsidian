# 📘 Notes: Smallest Number with Sum `s` and Digits `d`

### 🔹 Problem Statement

- Input: Two integers, `d` (number of digits) and `s` (sum of digits).
- Task: Find the **smallest number** with exactly `d` digits such that the sum of its digits equals `s`.
- Output: The smallest number formed or `"Not possible"` if it cannot be formed.
- Example:  
    Input:  
    5 6  
    Output:  
    10005

---

### 🔹 Key Concepts

1. **Digit Constraints** → Each digit is between 0–9, except the first digit cannot be 0.
2. **Greedy Approach (Right-to-Left)** → Start filling digits from the **least significant digit (rightmost)** to minimize the number.
3. **Feasibility Check** → Sum `s` must satisfy: `1 <= s <= 9*d` (if `s` is too big or too small, it’s impossible).

---

### 🔹 Step-by-Step Approach

1. Check if forming the number is possible:
    - If `s == 0` and `d > 1` → Not possible
    - If `s > 9*d` → Not possible
2. Initialize an array `digits[d]` to store each digit.
3. Start from the **last index** (rightmost digit) and fill digits greedily:
    - Take the minimum of 9 or remaining sum `s` for the current digit.
    - Subtract the chosen value from `s`.
4. After filling all digits, check if first digit is zero:
    - If so, adjust by moving 1 from a non-zero digit to the first digit to ensure no leading zero.
5. Print the digits array as the number.

---

### 🔹 Example Walkthrough

Input: `d=5, s=6`
- Start with digits array: `[0,0,0,0,0]`
- Fill rightmost digit first: `[0,0,0,0,6]`
- Remaining sum: 0
- Ensure first digit is non-zero: `[1,0,0,0,5]` ✅

Output: `10005`

---

# 🖥 Solutions

---

```embed
title: "Smallest number | Problem of the Day | GeeksForGeeks"
image: "https://i.ytimg.com/vi/CgaYmx0AkGA/maxresdefault.jpg?sqp=-oaymwEmCIAKENAF8quKqQMa8AEB-AH-CYAC0AWKAgwIABABGGkgaShpMA8=&rs=AOn4CLALwivAMSWDM7F8b98EIICntqoHGg"
description: "Given two integers s and d. The task is to find the smallest number such that the sum of its digits is s and the number of digits in the number are d. Return..."
url: "https://youtu.be/CgaYmx0AkGA"
favicon: ""
aspectRatio: "56.25"
```


### ✅ Python

```python
d = int(input())
s = int(input())

if s == 0 and d > 1 or s > 9*d:
    print("Not possible")
else:
    digits = [0]*d
    for i in range(d-1, -1, -1):
        if s > 9:
            digits[i] = 9
            s -= 9
        else:
            digits[i] = s
            s = 0
    if digits[0] == 0:
        for i in range(d):
            if digits[i] > 0:
                digits[i] -= 1
                digits[0] = 1
                break
    print("".join(map(str, digits)))

```

---

### ✅ C++

```cpp
#include <iostream>  
using namespace std;

int main() {  
	int d, s;  
	cin >> d >> s;
	if ((s == 0 && d > 1) || s > 9*d) {
	    cout << "Not possible" << endl;
	    return 0;
	}
	int remaining = s;
	for (int i = 0; i < d; i++) {
	    int digit;
	    int max_for_rest = 9 * (d - i - 1);
	    if (remaining > max_for_rest) {
	        digit = remaining - max_for_rest;
	    } else {
	        digit = 0;
	    }
	    if (i == 0 && digit == 0 && d > 1) digit = 1; 
	    // first digit cannot be 0
	    remaining -= digit;
	    cout << digit;
	}
	cout << endl;
	return 0;
}

```

---

### ✅ Java

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int d = sc.nextInt();
        int s = sc.nextInt();
        if ((s == 0 && d > 1) || s > 9*d) {
            System.out.println("Not possible");
            return;
        }
        int[] digits = new int[d];
        for (int i = d-1; i >= 0; i--) {
            if (s > 9) {
                digits[i] = 9;
                s -= 9;
            } else {
                digits[i] = s;
                s = 0;
            }
        }
        if (digits[0] == 0) {
            for (int i = 0; i < d; i++) {
                if (digits[i] > 0) {
                    digits[i]--;
                    digits[0] = 1;
                    break;
                }
            }
        }
        for (int i = 0; i < d; i++) System.out.print(digits[i]);
    }
}

```

---

✅ **Explanation:**

- **Right-to-left greedy filling** ensures the smallest number.
- Adjust the first digit if it is zero to avoid leading zeros.
- Checks handle impossible cases efficiently.