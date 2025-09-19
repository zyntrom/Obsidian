## 📒 Notes

### **Key Definitions**

1. **Proper Fraction** → numerator < denominator.  
    Example: 2/5 → proper fraction.
2. **Improper Fraction** → numerator ≥ denominator.  
    Example: 7/3 → improper fraction.
3. **Mixed Fraction** → representation of an improper fraction with a whole number and a proper fraction.  
    Example: 7/3 → 2 1/3.

---

### **Steps / Approach**

1. **Input**: numerator (`num`) and denominator (`den`).
2. **Check proper or improper**:
    - If `num < den` → proper fraction.
    - Else → improper fraction.
3. **For proper fraction**:
    - Find GCD of numerator and denominator.
    - Divide both by GCD → reduced form.
    - Print → `Proper a/b`.
4. **For improper fraction**:
    - Compute whole = `num // den`.
    - Compute remainder = `num % den`.
    - If remainder = 0 → fraction is just an integer (no fractional part).
    - Otherwise:
        - Reduce remainder/den using GCD.
        - Print → `Improper w a/b`.

---

### **Helper Function**

- **GCD (Greatest Common Divisor)** → Euclidean Algorithm:
    
```python
    gcd(a, b):     
	    while b != 0:         
		    a, b = b, a % b     
	    return a
```

---

## ✅ Example Walkthrough

Input: `2 4`

- Check: 2 < 4 → Proper fraction.
- GCD(2, 4) = 2.
- Reduced fraction = 2/2 ÷ 4/2 = 1/2.
- Output: **Proper 1/2**.

Input: `7 3`

- Check: 7 ≥ 3 → Improper fraction.
- Whole = 7 // 3 = 2.
- Remainder = 7 % 3 = 1.
- GCD(1, 3) = 1. → Fraction = 1/3.
- Output: **Improper 2 1/3**.

---

## 💻 Solutions in Different Languages

---

### **Python**

```py
import math

def fraction(num, den):
    if num < den:
        g = math.gcd(num, den)
        num //= g
        den //= g
        print(f"Proper {num}/{den}")
    else:
        whole = num // den
        remainder = num % den
        if remainder == 0:
            print(f"Improper {whole}")
        else:
            g = math.gcd(remainder, den)
            remainder //= g
            den //= g
            print(f"Improper {whole} {remainder}/{den}")

# Example
num, den = map(int, input().split())
fraction(num, den)

```
---

### **C++**

`#include <iostream> #include <algorithm> using namespace std;  int main() {     int num, den;     cin >> num >> den;      if (num < den) {         int g = __gcd(num, den);         num /= g;         den /= g;         cout << "Proper " << num << "/" << den << endl;     } else {         int whole = num / den;         int remainder = num % den;         if (remainder == 0) {             cout << "Improper " << whole << endl;         } else {             int g = __gcd(remainder, den);             remainder /= g;             den /= g;             cout << "Improper " << whole << " " << remainder << "/" << den << endl;         }     }      return 0; }`

---

### **Java**

`import java.util.Scanner;  public class Main {     public static int gcd(int a, int b) {         while (b != 0) {             int temp = b;             b = a % b;             a = temp;         }         return a;     }      public static void main(String[] args) {         Scanner sc = new Scanner(System.in);         int num = sc.nextInt();         int den = sc.nextInt();          if (num < den) {             int g = gcd(num, den);             num /= g;             den /= g;             System.out.println("Proper " + num + "/" + den);         } else {             int whole = num / den;             int remainder = num % den;             if (remainder == 0) {                 System.out.println("Improper " + whole);             } else {                 int g = gcd(remainder, den);                 remainder /= g;                 den /= g;                 System.out.println("Improper " + whole + " " + remainder + "/" + den);             }         }          sc.close();     } }`