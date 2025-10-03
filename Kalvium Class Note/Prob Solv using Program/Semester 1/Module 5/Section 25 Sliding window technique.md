# 📒 Notes: Sliding Window Technique

---

## 🔹 What is Sliding Window Technique?

The **Sliding Window Technique** is an **efficient method** to process arrays, strings, or other linear data structures by considering a **subarray/window** of elements at a time.

- Reduces redundant calculations → improves **O(n²) → O(n)** efficiency.
- The “window” slides across the data: **new elements enter**, **old elements exit**.
- Useful for **maximum/minimum sums, longest/shortest subarrays, substring problems**, etc.

**Analogy:** Like focusing your eyesight on a few words while reading, moving forward as needed.
```embed
title: "The Sliding Window Approach in 120 Seconds"
image: "https://i.ytimg.com/vi/YDFq9EO8-zg/maxresdefault.jpg"
description: "Today we explore 3. Longest Substring Without Repeating Characters where we explore the Sliding Window approach in coding. Don't miss the opportunity to lear..."
url: "https://youtu.be/YDFq9EO8-zg"
favicon: ""
aspectRatio: "56.25"
```

---

## 🔹 Types of Sliding Windows

|Type|Description|Example Problem|
|---|---|---|
|**Fixed-Size Window**|Window size is constant; slides one step at a time|Max sum of **k consecutive elements** in an array|
|**Variable-Size Window**|Window size grows or shrinks based on conditions|Smallest subarray with sum ≥ target|

---

## 🔹 1️⃣ Fixed-Size Sliding Window

**Problem:** Find **maximum sum of 3 consecutive elements** in `[2, 1, 5, 1, 3, 2]`.

**Approach:**
1. Calculate sum of **first window** of size `k = 3` → `[2, 1, 5] = 8`
2. Slide window: remove leftmost element, add new element:
    - `[1, 5, 1] → 7` → max remains 8
    - `[5, 1, 3] → 9` → max becomes 9
    - `[1, 3, 2] → 6` → max remains 9

**Efficiency:**

- Instead of recalculating sum entirely, **subtract outgoing + add incoming** → O(n)

**Pseudo code:**

```
function fixedSlidingWindow(data, windowSize):
    windowSum = sum of first windowSize elements
    maxSum = windowSum

    for i = windowSize to length(data)-1:
        windowSum = windowSum - data[i-windowSize] + data[i]
        maxSum = max(maxSum, windowSum)

    return maxSum

```

---

## 🔹 2️⃣ Variable-Size Sliding Window

**Problem:** Find **smallest subarray with sum ≥ target = 7** in `[2, 1, 5, 2, 3, 2]`.

**Approach:**

1. Initialize empty window → `currentSum = 0`, `minLength = ∞`
2. Expand window: add elements until `currentSum ≥ target`
3. Shrink window from left while still satisfying condition
4. Track minimum window length

**Dry run:**

- Add 2 → sum = 2 (< 7) → expand
- Add 1 → sum = 3 (< 7) → expand
- Add 5 → sum = 8 (≥7) → record length = 3, shrink left → sum = 6 (<7)
- Add 2 → sum = 8 → shrink left → sum = 7 → record length = 2
- End → **smallest subarray length = 2**

**Efficiency:**

- Each element added **once** and removed **once** → O(n)

**Pseudo code:**

```
function variableSlidingWindow(data, target):
    start = 0
    currentSum = 0
    minLength = infinity

    for end in 0 to length(data)-1:
        currentSum += data[end]

        while currentSum >= target:
            minLength = min(minLength, end - start + 1)
            currentSum -= data[start]
            start += 1

    return minLength

```

---

## 🔹 Key Insights

- **Fixed-Size Window:** Best when window size `k` is known in advance
- **Variable-Size Window:** Best when condition defines window boundaries
- Reduces **redundant calculations** → dynamic sum or data update
- Time Complexity: **O(n)** for both types (each element visited max twice)
- Space Complexity: **O(1)**

---

## 🔹 Applications

|Problem Type|Use Case|
|---|---|
|Maximum sum of k consecutive elements|Fixed-size window|
|Smallest subarray with sum ≥ target|Variable-size window|
|Longest substring without repeating characters|Variable-size window|
|Sliding averages / moving sums|Fixed-size window|
|Dynamic range queries|Variable-size window|
```embed
title: "Sliding Window Technique"
image: "https://i.ytimg.com/vi/dOonV4byDEg/maxresdefault.jpg"
description: "The Sliding Window technique is a key tool in algorithmic problem-solving that can significantly speed up calculations and improve performance. This techniqu..."
url: "https://youtu.be/dOonV4byDEg"
favicon: ""
aspectRatio: "56.25"
```

---

## 🔹 Summary

- **Sliding window** moves a subset of elements through a larger dataset efficiently
- **Fixed-size:** constant window, update dynamically
- **Variable-size:** window grows/shrinks based on condition
- **Optimizes O(n² → O(n))**, keeps **O(1) extra space**
- Crucial for **subarray, substring, sum, and max/min problems**