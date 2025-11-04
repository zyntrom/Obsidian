## 1. Two Sum

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

## 2. Palindrome Number

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

## 3. Roman to integer

```java
class Solution {
    public int romanToInt(String s) {
        HashMap<Character, Integer> map = new HashMap<>();
        map.put('I', 1);
        map.put('V', 5);
        map.put('X', 10);
        map.put('L', 50);
        map.put('C', 100);
        map.put('D', 500);
        map.put('M', 1000);
        int total = 0;
        for (int i = 0; i < s.length(); i++) {
            int value = map.get(s.charAt(i));
            if (i + 1 < s.length()) {
                int nextValue = map.get(s.charAt(i + 1));
                if (value < nextValue) {
                    total -= value;
                } else {
                    total += value;
                }
            } else {
                total += value;
            }
        }
        return total;
    }
}

```

## 4. Longest Common Prefix

```java
class Solution {
    public String longestCommonPrefix(String[] strs) {
        if (strs.length == 0) return "";
        String prefix = strs[0];
        for (int i = 1; i < strs.length; i++) {
            while (strs[i].indexOf(prefix) != 0) {
                prefix = prefix.substring(0, prefix.length() - 1)
                if (prefix.isEmpty()) {
                    return "";
                }
            }
        }
        return prefix;
    }
}
```

## 5. Valid Parentheses

```java
class Solution {
    public boolean isValid(String s) {
        int l = s.length();
        Stack<Character> stack = new Stack<>();
        for (int i = 0; i < l; i++) {
            char c = s.charAt(i);
            
            if (c == '(' || c == '{' || c == '[') {
                stack.push(c);
            }
            else if (c == ')' || c == '}' || c == ']') {
                if (stack.isEmpty()) return false;
                char top = stack.peek();
                if ((c == ')' && top == '(') || 
                    (c == ']' && top == '[') || 
                    (c == '}' && top == '{')) {
                    stack.pop();
                } else {
                    return false;
                }
            }
        }
        
        return stack.isEmpty();
    }
}

```

## 6. Merge Two Sorted Lists

```java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode() {}
 *     ListNode(int val) { this.val = val; }
 *     ListNode(int val, ListNode next) { this.val = val; this.next = next; }
 * }
 */
 
class Solution {
    public ListNode mergeTwoLists(ListNode list1, ListNode list2) {
        ListNode dummy = new ListNode(-1);
        ListNode curr = dummy;
        while (list1 != null && list2 != null) {
            if (list1.val <= list2.val) {
                curr.next = list1;
                list1 = list1.next;
            } else {
                curr.next = list2;
                list2 = list2.next;
            }
            curr = curr.next;
        }
        if (list1 != null) {
            curr.next = list1;
        } else {
            curr.next = list2;
        }
        return dummy.next;
    }
}

```

## 7. 