# 📘 Notes: Powerful Digit Counts

### 🔹 Problem Statement

- Input: A positive integer `N` (1 < N < 10).
- Output: Print all **N positive integers** `x` such that `x^N` has exactly `N` digits.

**Examples:**

- Input: `2` → Output: `16, 25, 36, 49, 64, 81`
    - Explanation: 16 = 4² (2 digits), 25 = 5² (2 digits), etc.
- Input: `3` → Output: 125, 216, 343, … (all 3-digit cubes)

---

### 🔹 Key Concepts

1. **Power Calculation** → Use `i^N` (Python: `i**N`, C++/Java: `pow(i,N)`).
2. **Digit Counting** → Check number of digits in `i^N` using:
    - Convert to string → `len(str(num))`
    - Or repeatedly divide by 10 until zero → count digits.
3. **Loop** → Iterate `i` from 1 to 9 (or until `i^N` exceeds N digits).
4. **Condition Check** → Only print if the number of digits of `i^N` equals `N`.

---

### 🔹 Algorithm / Approach

1. Read input `N`.
2. For `i` starting from 1 to 10:
    - Compute `ans = i^N`.
        
    - Count digits of `ans`.
        
    - If digits == N → print `ans`.
        
3. Repeat until all numbers in the range are checked.
    

---

# 🖥 Solutions

---

### ✅ Python

`N = int(input())  for i in range(1, 10):     ans = i ** N     if len(str(ans)) == N:         print(ans)`

---

### ✅ C++

`#include <iostream> #include <cmath> using namespace std;  int main() {     int N;     cin >> N;      for(int i = 1; i < 10; i++) {         int ans = pow(i, N);         int temp = ans, digits = 0;         while(temp > 0) {             temp /= 10;             digits++;         }         if(digits == N) {             cout << ans << endl;         }     }     return 0; }`

---

### ✅ Java

`import java.util.Scanner;  public class Main {     public static void main(String[] args) {         Scanner sc = new Scanner(System.in);         int N = sc.nextInt();          for(int i = 1; i < 10; i++) {             long ans = (long)Math.pow(i, N);             int digits = String.valueOf(ans).length();             if(digits == N) {                 System.out.println(ans);             }         }     } }`

---

### 🔹 Explanation

- The loop iterates through candidate numbers `i = 1 to 9`.
    
- `i^N` is calculated.
    
- We count digits using string conversion or division.
    
- Only numbers where `i^N` has exactly `N` digits are printed.
    
- This works for N < 10 because for N ≥ 10, `i^N` exceeds 10 digits.