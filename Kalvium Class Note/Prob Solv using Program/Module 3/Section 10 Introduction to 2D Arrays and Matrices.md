# 📘 Notes: 2D Arrays and Matrices

## 🔹 Definition

- A **2D Array** (Matrix/Grid) is an **array of arrays**.
- Data is stored in **rows and columns**, like a table.
- Each element is accessed using **two indices** → `array[row][col]`.
- Useful for:
    - Cinema hall seating
    - Spreadsheets
    - Chessboard
    - Image representation (pixels)

---

## 🔹 Structure of a 2D Array

- Think of it as:
```
Row 0 → [a00, a01, a02, ...] Row 1 → [a10, a11, a12, ...] Row 2 → [a20, a21, a22, ...]
```
- **First index** = Row number
- **Second index** = Column number

---

## 🔹 Declaration & Initialization

### In Python 🐍

```cpp
# Empty 2D array 
matrix = []  
# Predefined 2D array 
matrix = [     
	[1, 2, 3],     
	[4, 5, 6],     
	[7, 8, 9] 
]
```
### In cpp 💻

```cpp
// Declaration 
int matrix[3][4]; // 3 rows, 4 columns  // Initialization 
int matrix[3][3] = {     
	{1, 2, 3},     
	{4, 5, 6},     
	{7, 8, 9} 
};
```

---

## 🔹 Input & Output of 2D Arrays

### Python Example

```python
rows = int(input("Enter rows: ")) 
cols = int(input("Enter columns: "))  
matrix = []  
for i in range(rows):    
	row=list(map(int,input().split()))
	matrix.append(row)  # Print matrix for row in matrix:     

for i in range(rows):
	print(*matrix[i])
	
```

### cpp Example

```cpp
#include <iostream>
using namespace std;

int main() {
    int rows, cols;
    cin >> rows >> cols;
    int matrix[100][100]; // Max size
    // Input
    for (int i=0; i<rows; i++) {
        for (int j=0; j<cols; j++) {
            cin >> matrix[i][j];
        }
    }
    // Output
    for (int i=0; i<rows; i++) {
        for (int j=0; j<cols; j++) {
            cout << matrix[i][j] << " ";
        }
        cout << endl;
    }
}

```
---

## 🔹 Processing a 2D Array

- Uses **nested loops**
    - Outer loop → Rows
    - Inner loop → Columns
- Example:
    - Printing all elements
    - Calculating row sums / column sums
    - Finding border elements

```embed
title: "iGCSE Computer Science - Python - 2D Arrays"
image: "https://i.ytimg.com/vi/2tPOjPJ6D1E/maxresdefault.jpg"
description: "This tutorial goes through some iGCSE-style problems pertaining to 2D arrays."
url: "https://youtu.be/2tPOjPJ6D1E"
favicon: ""
aspectRatio: "56.25"
```

```embed
title: "2D Arrays in cpp | 2D array addition & Subtraction"
image: "https://i.ytimg.com/vi/OJC84pYXB_U/maxresdefault.jpg"
description: "Support Simple Snippets by Donations -Google Pay UPI ID - tanmaysakpal11@okiciciPayPal - paypal.me/tanmaysakpal11--------------------------------------------..."
url: "https://youtu.be/OJC84pYXB_U"
favicon: ""
aspectRatio: "56.25"
```


---

## 🔹 Real-Life Applications

- **Cinema hall seating** → rows & seat numbers
- **Chessboard/board games** → 8x8 grid
- **Image representation** → pixels in matrix form
- **Spreadsheets** → Excel tables

---

## 🔹 Example Problem – Treasure Island Pathfinding

- Represent island as a 2D array:
    - `0 = Safe zone`
    - `1 = Moderate danger`
    - `2 = High danger`
- Find safest path from `(0,0)` → `(rows-1, cols-1)`.
- Steps:
    1. Initialize grid (matrix).
    2. Use **recursion / backtracking** to explore paths.
    3. Calculate total risk for each path.
    4. Mark safest path with `-1`.

---

## 🔹 Summary (Quick Revision)

- **2D Array = Array of arrays** (rows × columns).
- **Access element** → `arr[row][col]`.
- **Nested loops** are key for traversal.
- **Applications**: games, images, seating, spreadsheets.
- **Exam tip**: Always specify **row index first, then column index**.