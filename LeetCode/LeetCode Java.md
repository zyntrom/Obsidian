## 1.Two Sum

```java
public class TwoSum {
    public static int[] twoSum(int[] nums, int target) {
        HashMap<Integer, Integer> map = new HashMap<>();
        for (int i = 0; i < nums.length; i++) {
            int num = nums[i];
            int complement = target - num;
            if (map.containsKey(complement)) {
                return new int[] { map.get(complement), i };
            }
          
	        map.put(num, i);
        }
        return new int[] {};
    }
}
```

## 2.Palindrome Number

```java
class Solution {
    public boolean isPalindrome(int x) {
        int rev = 0;
        int n = x;
        if (x < 0) {
            return false;
        }
        while (n != 0) {
            rev = rev * 10 + (n % 10);
            n = n / 10;
        }
        if (rev == x) {
            return true;
        } else {
            return false;
        }
    }
}
```

## 3.Roman to integer

```java

```