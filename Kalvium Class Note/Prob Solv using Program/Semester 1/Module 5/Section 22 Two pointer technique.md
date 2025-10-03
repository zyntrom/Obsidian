# 📒 Notes: Two-Pointer Technique

---

## 🔹 Concept

The **Two-Pointer Technique** is an efficient approach for solving problems on arrays, strings, or linked lists by using **two reference variables (pointers)** that traverse the data either in the same direction or opposite directions.

It reduces **time complexity** by avoiding nested loops and often achieves **O(n)** solutions instead of **O(n²)**.

**Analogy:**

- Searching for a book in a library from both ends → quickly narrow search space.

---

## 🔹 Types of Two-Pointer Techniques

1. **Left & Right Pointers (Opposite Direction)**
    - Pointers start at **opposite ends** of a data structure.
    - Move toward each other based on a **condition**.
    - Used in sorted arrays, palindrome checking, two-sum problems, etc.
2. **Fast & Slow Pointers (Same Direction)**
    - Both pointers move in the **same direction**, but at **different speeds**.
    - Common in linked list problems (e.g., detecting cycles, finding middle node).

> Today’s focus: **Left & Right Pointers**

---

## 🔹 How Left & Right Pointers Work

**Algorithm:**

1. Initialize `left` at the start (0) and `right` at the end (`n-1`).
2. While `left < right`:
    - Check a condition using elements at `left` and `right`.
    - If condition met → perform action (e.g., return result).
    - If sum/condition too small → move `left` right to increase value.
    - If sum/condition too large → move `right` left to decrease value.
3. Stop when pointers meet or result found.

```embed
title: "Two Pointers in 7 minutes | LeetCode Pattern"
image: "https://i.ytimg.com/vi/QzZ7nmouLTI/maxresdefault.jpg"
description: "Master DSA Patterns: https://algomaster.io/GitHub repository: https://github.com/ashishps1/awesome-leetcode-resourcesIn this video, I talk about the two poin..."
url: "https://youtu.be/QzZ7nmouLTI"
favicon: ""
aspectRatio: "56.25"
```

```embed
title: "Two Pointers in 7 minutes | LeetCode Pattern"
image: "https://i.ytimg.com/vi/QzZ7nmouLTI/maxresdefault.jpg"
description: "Master DSA Patterns: https://algomaster.io/GitHub repository: https://github.com/ashishps1/awesome-leetcode-resourcesIn this video, I talk about the two poin..."
url: "https://youtu.be/QzZ7nmouLTI"
favicon: ""
aspectRatio: "56.25"
```

---

### Example: Two-Sum Problem (Sorted Array)

**Problem:** Find two numbers in a sorted array that sum to a target value.

**Input:**

```
arr = [1,3,4,6,8,10,13,14,15], target = 17
```

**Steps:**

- `left = 0`, `right = 7` → arr[left] + arr[right] = 1 + 15 = 16 → too small → move left
- `left = 1`, `right = 7` → 3 + 15 = 18 → too large → move right
- `left = 1`, `right = 6` → 3 + 14 = 17 → found pair ✅

**Output:** `(3, 14)`

**Time Complexity:** O(n)  
**Space Complexity:** O(1)

---

## 🔹 Applications

1. **Palindrome Checking**
    - Compare characters from **both ends** moving inward.
    - Stop at first mismatch.
    - **Time Complexity:** O(n/2) → O(n)
2. **Two-Sum Problem** (sorted array)
    - Find pairs with a given sum efficiently.
3. **Container With Most Water**
    - Two pointers at both ends → always move the shorter line inward.
4. **Trapping Rainwater**
    - Track max height from left and right → compute trapped water in O(n).
5. **Three-Sum Problem**
    - Fix one element → use left & right pointers for remaining array.

---

## 🔹 Example Problem: Palindrome Check

**Problem:** Determine if a string reads the same forward and backward.
**Approach:**
1. `left = 0`, `right = length(str) - 1`
2. While `left < right`:
    - If `str[left] != str[right]` → return false
    - Else: `left++`, `right--`
3. Return true if loop completes

**Pseudo Code:**

```
function isPalindrome(str):
    left = 0
    right = length(str) - 1
    
    while left < right:
        if str[left] != str[right]:
            return false
        left = left + 1
        right = right - 1
    
    return true

```

**Explanation:**

- Compares **pairs of characters** from opposite ends
- Stops immediately if mismatch found
- Only **half of the string** is checked → O(n) time, O(1) space

---

## 🔹 Complexity Analysis

|Aspect|Complexity|
|---|---|
|Time Complexity|O(n)|
|Space Complexity|O(1)|
|Advantage|Avoids nested loops (O(n²))|
|Suitable For|Sorted arrays, strings, linked lists|

---

## 🔹 Key Takeaways

- **Efficient searching & comparison** → O(n) instead of O(n²)
- **Left & Right pointers:** start from opposite ends, move inward
- **Fast & Slow pointers:** same direction, different speeds
- **Applications:** palindrome, two-sum, container with most water, trapping rainwater, three-sum, etc.
- Only **constant extra space** needed

---

### ✅ Optional: Diagram

- Left pointer at start, right pointer at end
- Arrows converge toward the middle
- Compare elements → move pointers according to condition