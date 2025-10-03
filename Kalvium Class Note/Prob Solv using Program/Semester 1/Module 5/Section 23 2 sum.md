# 📒 Notes: 2-Sum Problem Using Two Pointers

---

## 🔹 Problem Statement

Given a **sorted array** `nums` and a target value `target`, find the **indices of two numbers** such that their sum equals the target.

- Return `-1` if the array is empty or no solution exists.
- **Each input has exactly one solution.**

**Example 1:**

```
Input: nums = [2,7,11,19], target = 9 Output: 0 1
```

**Example 2:**

```
Input: nums = [1,3,5,8,12], target = 8 Output: 1 2
```

---

## 🔹 Approach (Using Two Pointers)

1. **Ensure the array is sorted**.
2. **Initialize two pointers**:
    - `left = 0` (start of array)
    - `right = n-1` (end of array)
3. **Iterate while `left < right`**:
    - Calculate `sum = nums[left] + nums[right]`
    - **If sum == target** → return `[left, right]`
    - **If sum < target** → move `left` right (`left++`)
    - **If sum > target** → move `right` left (`right--`)
4. If pointers cross and no solution → return `-1`

---

## 🔹 Step-by-Step Example

**Array:** `[1, 3, 5, 8, 12]`, **Target:** `8`

|Step|left|right|nums[left]+nums[right]|Action|
|---|---|---|---|---|
|1|0|4|1+12=13|>8 → move right left|
|2|0|3|1+8=9|>8 → move right left|
|3|0|2|1+5=6|<8 → move left right|
|4|1|2|3+5=8|==8 → found, return [1,2]|

---

## 🔹 Pseudo Code

`function twoSum(nums, target):     left = 0     right = length(nums) - 1          while left < right:         sum = nums[left] + nums[right]                  if sum == target:             return [left, right]         else if sum < target:             left = left + 1         else:             right = right - 1          return -1`

---

## 🔹 Time & Space Complexity

|Aspect|Complexity|
|---|---|
|Time Complexity|O(n)|
|Space Complexity|O(1)|
|Reason|Single pass through array, constant extra space|

---

## 🔹 Key Points

- Only works efficiently if **array is sorted**.
    
- Reduces the naive **O(n²)** approach to **O(n)**.
    
- Left pointer increases to increase sum; right pointer decreases to decrease sum.
    
- Ideal for **2-sum, two-pointer based problems** like 3-sum (fix one element, two-pointer on remainder).