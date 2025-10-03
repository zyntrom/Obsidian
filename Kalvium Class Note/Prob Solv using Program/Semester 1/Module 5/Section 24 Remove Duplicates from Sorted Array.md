# 📒 Notes: Remove Duplicates from Sorted Array

---

## 🔹 Problem Statement

Given a **sorted array** `nums` in non-decreasing order, **remove duplicates in-place** such that each unique element appears only once.

- Keep the **relative order** of elements unchanged.
- Return the **number of unique elements** in the array.
- **Do not use extra space** (in-place modification).

**Example 1:**

```
Input: nums = [1,1,2] 
Output: 2 Explanation: nums = [1,2,_], number of unique elements = 2
```

**Example 2:**

```
Input: nums = [0,0,1,1,1,2,2,3,3,4] 
Output: 5 Explanation: nums = [0,1,2,3,4,_,_,_,_,_], number of unique elements = 5
```

---

## 🔹 Approach (Two-Pointer Technique)

Since the array is **sorted**, all duplicates are consecutive.

1. **Initialize two pointers**:
    - `i = 0` → keeps track of the **last unique element**
    - `j = 1` → scans through the array
2. **Traverse the array with `j`**:
    - If `nums[j] != nums[i]`:
        - Increment `i`
        - Copy `nums[j]` to `nums[i]`
3. **Return `i + 1`**, the number of unique elements.

**Why it works:**

- Pointer `i` ensures all unique elements are shifted to the **front of the array**.
- Pointer `j` scans the rest of the array, skipping duplicates.
- No extra memory is used → **O(1) space**.

---

## 🔹 Step-by-Step Example

**Array:** `[0,0,1,1,1,2,2,3,3,4]`

|Step|i|j|Action|Array State|
|---|---|---|---|---|
|1|0|1|nums[1]==nums[0] → skip|[0,0,1,1,1,2,2,3,3,4]|
|2|0|2|nums[2]!=nums[0] → i++ → copy|[0,1,1,1,1,2,2,3,3,4]|
|3|1|3|nums[3]==nums[1] → skip|[0,1,1,1,1,2,2,3,3,4]|
|4|1|5|nums[5]!=nums[1] → i++ → copy|[0,1,2,1,1,2,2,3,3,4]|
|5|2|7|nums[7]!=nums[2] → i++ → copy|[0,1,2,3,1,2,2,3,3,4]|
|6|3|9|nums[9]!=nums[3] → i++ → copy|[0,1,2,3,4,2,2,3,3,4]|

- Final unique elements = `[0,1,2,3,4]`
    
- Count = `i + 1 = 5`
    

---

## 🔹 Pseudo Code

```
function removeDuplicates(nums):
    if length(nums) == 0:
        return 0

    i = 0
    for j from 1 to length(nums)-1:
        if nums[j] != nums[i]:
            i = i + 1
            nums[i] = nums[j]

    return i + 1

```

```embed
title: "Remove Duplicates from Sorted Array - Leetcode 26 - Python"
image: "https://i.ytimg.com/vi/DEJAZBq0FDA/maxresdefault.jpg"
description: "🚀 https://neetcode.io/ - A better way to prepare for Coding Interviews🐦 Twitter: https://twitter.com/neetcode1🥷 Discord: https://discord.gg/ddjKRXPqtk🐮 S..."
url: "https://youtu.be/DEJAZBq0FDA"
favicon: ""
aspectRatio: "56.25"
```


---

## 🔹 Time & Space Complexity

|Aspect|Complexity|
|---|---|
|Time Complexity|O(n)|
|Space Complexity|O(1)|
|Reason|Single pass through array, in-place modification|

---

## 🔹 Key Points

- **Sorted array** → consecutive duplicates → easy to remove in-place.
- Two-pointer technique:
    - `i` → stores last unique element
    - `j` → iterates to find new unique elements
- In-place modification avoids extra memory allocation.
- Edge cases:
    - Empty array → return 0
    - Array with one element → return 1
    - No duplicates → array remains unchanged