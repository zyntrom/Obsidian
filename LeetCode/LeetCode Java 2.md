## 11. Length of Last Word

```cpp
class Solution {
public:
    int lengthOfLastWord(string s) {
        int n = s.length();
        int count = 0;
        int p = n - 1;
        for (int i = 0; i < n; i++) {
            if (s[i] != ' ') {
                p = i;
            }
        }
        for (int i = p; i >= 0; i--) {
            if (s[i] == ' ') {
                break;
            }
            count++;
        }
        return count;
    }
};

```

## 12. Plus One

```java
class Solution {
    public int[] plusOne(int[] digits) {
        int n = digits.length;
        // Traverse from last digit
        for (int i = n - 1; i >= 0; i--) {
            // If digit is less than 9, simply increment and return
            if (digits[i] < 9) {
                digits[i]++;
                return digits;
            }
            
            // If digit is 9, set it to 0 and continue loop (carry)
            digits[i] = 0;
        }
        // If all digits were 9, we need an extra leading 1
        int[] result = new int[n + 1];
        result[0] = 1; // rest will be 0 by default
        return result;
    }
}

```

## 13. Add Binary

```java
class Solution {
    public String addBinary(String a, String b) {
        StringBuilder result = new StringBuilder();
        
        int i = a.length() - 1;
        int j = b.length() - 1;
        int carry = 0;
        // Loop through both strings from right to left
        while (i >= 0 || j >= 0 || carry == 1) {
            int sum = carry;
            if (i >= 0) {
                sum += a.charAt(i--) - '0'; // convert char to int
            }
            if (j >= 0) {
                sum += b.charAt(j--) - '0';
            }
            // Append the current bit (sum % 2)
            result.append(sum % 2);
            // Update carry
            carry = sum / 2;
        }
        // Reverse the result to get correct order
        return result.reverse().toString();
    }
}

```

## 14. Sqrt(x)

```java
class Solution {
    public int mySqrt(int x) {
        if (x < 2) return x;
        int left = 1, right = x / 2;
        int ans = 0;
        while (left <= right) {
            int mid = left + (right - left) / 2;
            long sq = (long) mid * mid; // avoid overflow
            if (sq == x) {
                return mid;
            } else if (sq < x) {
                ans = mid;       // store last valid value
                left = mid + 1;
            } else {
                right = mid - 1;
            }
        }
        return ans;
    }
}

```

## 15.