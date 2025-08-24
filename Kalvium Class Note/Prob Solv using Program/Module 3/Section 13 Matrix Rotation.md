# Matrix Rotation – Notes

## 1. Definition

- **Matrix Rotation (90° clockwise)** transforms a square matrix of size n × n into a new arrangement.
- Example:

Input:

`1 2 3 4 5 6 7 8 9`

Output (after 90° clockwise rotation):

`7 4 1 8 5 2 9 6 3`

---

## 2. Constraints

- 1 ≤ n ≤ 1000
- -1000 ≤ matrix[i][j] ≤ 1000

---

## 3. Approach

To rotate a matrix 90° clockwise:

1. **Transpose the matrix** → Convert rows into columns.
```
A[i][j] → A[j][i]
```
2. **Reverse each row** of the transposed matrix.

This gives the rotated matrix.

---

## 4. Example Walkthrough

Given matrix:

```
1 2 3 4 5 6 7 8 9
```

Step 1: Transpose →

```
1 4 7 2 5 8 3 6 9
```

Step 2: Reverse each row →

```
7 4 1 8 5 2 9 6 3
```

---

## 5. Implementation in Python

```python
# Matrix Rotation (90 degrees clockwise)  
def rotate_matrix(matrix):     
	n = len(matrix)          
# Step 1: Transpose     
	for i in range(n):         
		for j in range(i, n):             
			matrix[i][j], matrix[j][i] = matrix[j][i], matrix[i][j]          # Step 2: Reverse each row     
	for row in matrix:         
		row.reverse()          
	return matrix  # Example usage 
	n = 3 
	matrix = [     
		[1, 2, 3],     
		[4, 5, 6],     
		[7, 8, 9] 
	]  
	rotated = rotate_matrix(matrix) print("Rotated Matrix:") for row in rotated:     print(row)
```

---

## 6. Implementation in C++

`#include <iostream> #include <vector> using namespace std;  void rotateMatrix(vector<vector<int>>& matrix) {     int n = matrix.size();          // Step 1: Transpose     for (int i = 0; i < n; i++) {         for (int j = i; j < n; j++) {             swap(matrix[i][j], matrix[j][i]);         }     }          // Step 2: Reverse each row     for (int i = 0; i < n; i++) {         reverse(matrix[i].begin(), matrix[i].end());     } }  int main() {     int n = 3;     vector<vector<int>> matrix = {         {1, 2, 3},         {4, 5, 6},         {7, 8, 9}     };          rotateMatrix(matrix);          cout << "Rotated Matrix:" << endl;     for (int i = 0; i < n; i++) {         for (int j = 0; j < n; j++) {             cout << matrix[i][j] << " ";         }         cout << endl;     }          return 0; }`

---

## 7. Time Complexity

- **Transpose**: O(n²)
    
- **Reverse rows**: O(n²)
    
- Total: **O(n²)**
    

---

## 8. Applications

- 🖼 Image rotation in graphics processing
    
- 🎮 Game development (rotating grids/boards)
    
- 🔢 Mathematical transformations in linear algebra