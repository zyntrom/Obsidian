# 📘 Notes: Binary Search in a 1-D Array

## 🔹 Definition

Binary Search is an efficient searching algorithm used on **sorted arrays**. It works by repeatedly dividing the search space into halves until the target element is found or the search space becomes empty.

---

## 🔹 Key Properties

- **Input Requirement**: Array must be sorted (ascending order in this case).
- **Time Complexity**:
    - Best Case: O(1) → element found at first mid check
    - Worst Case: O(log n) → search space halves each time
        
- **Space Complexity**: O(1) → iterative implementation requires constant extra space
    

---

## 🔹 Working Principle (Step-by-Step)

1. Start with two pointers:
    
    - `low = 0` (start of array)
        
    - `high = n-1` (end of array)
        
2. Find the middle index:
    
    - `mid = (low + high) / 2` (integer division)
        
3. Compare `arr[mid]` with target `x`:
    
    - If `arr[mid] == x` → return `mid` (found)
        
    - If `arr[mid] < x` → move to **right half** (`low = mid + 1`)
        
    - If `arr[mid] > x` → move to **left half** (`high = mid - 1`)
        
4. Repeat until `low > high` (search space exhausted).
    
5. If not found → return `-1`.
    

---

## 🔹 Algorithm (Iterative)

`BinarySearch(arr, n, x):     low = 0     high = n - 1     while low <= high:         mid = (low + high) // 2         if arr[mid] == x:             return mid         else if arr[mid] < x:             low = mid + 1         else:             high = mid - 1     return -1`

---

## 🔹 Example

Array: `[2, 5, 8, 12, 16, 23, 38, 56]`  
Target: `23`

Steps:

1. low = 0, high = 7 → mid = 3 → arr[3] = 12 < 23 → search right half
    
2. low = 4, high = 7 → mid = 5 → arr[5] = 23 → Found at index 5
    

**Answer = 5**

---

## 🔹 Advantages

- Much faster than Linear Search for large arrays.
    
- Time complexity O(log n).
    

---

## 🔹 Limitations

- Works only on **sorted arrays**.
    
- Not suitable for dynamic datasets (where elements are frequently inserted/deleted).
    

---

## 🔹 Comparison: Linear vs Binary Search

|Feature|Linear Search|Binary Search|
|---|---|---|
|Requirement|Works on any array|Needs sorted array|
|Time Complexity|O(n)|O(log n)|
|Best Case|O(1)|O(1)|
|Worst Case|O(n)|O(log n)|
|Use Case|Small/unsorted data|Large/sorted data|