# Matrix Multiplication – Notes

## 1. Definition

- **Matrix multiplication** combines two matrices to form a new matrix.
- Rule:
    - If A is an **m × n** matrix and B is an **n × p** matrix,
    - Then C = A × B is an **m × p** matrix.
- The number of **columns of A** must equal the number of **rows of B**.

---

## 2. Formula

For each element of the result matrix C:

```
C[i][j] = A[i][0] * B[0][j] + A[i][1] * B[1][j] + ... + A[i][n-1] * B[n-1][j]
```

This is the **dot product** of the i-th row of A and j-th column of B.

---

## 3. Example

Let:

```
A =  
[ [1, 2, 3],  
[4, 5, 6],  
[7, 8, 9] ]
```

```
B =  
[ [4, 5, 6],  
[7, 8, 9],  
[10, 11, 12] ]
```

Then:

```
C[0][0] = (1_4) + (2_7) + (3*10) = 4 + 14 + 30 = 48
```

---

## 4. Algorithm Steps

1. Create result matrix `C` with dimensions `rows(A) × cols(B)`.
2. Loop through each row `i` of A.
3. Loop through each column `j` of B.
4. For each C[i][j], compute dot product:
    sum( A[i][k] * B[k][j] ) for all `k`.
5. Store result in C[i][j].

---

## 5. Implementation in Python

```python
# Matrix Multiplication in Python  
A = [     
	[1, 2, 3],     
	[4, 5, 6],     
	[7, 8, 9] 
]  
B = [     
	[4, 5, 6],     
	[7, 8, 9],     
	[10, 11, 12] 
]  
rows, cols = len(A), len(B[0]) 
C = [[0 for _ in range(cols)] for _ in range(rows)]  
for i in range(rows):     
	for j in range(cols):         
		for k in range(len(B)):             
			C[i][j] += A[i][k] * B[k][j]  
			print("Resultant Matrix C:") 
for row in C:     
	print(row)
```

---

## 6. Implementation in cpp

```cpp
#include <iostream> 
using namespace std;  
int main() {     
	int A[3][3] = {{1, 2, 3}, {4, 5, 6}, {7, 8, 9}};     
	int B[3][3] = {{4, 5, 6}, {7, 8, 9}, {10, 11, 12}};     
	int C[3][3] = {0};      
	for (int i = 0; i < 3; i++) {         
		for (int j = 0; j < 3; j++) {             
			for (int k = 0; k < 3; k++) {                 
				C[i][j] += A[i][k] * B[k][j];             
			}         
		}     
	}      
	cout << "Resultant Matrix C:" << endl;     
	for (int i = 0; i < 3; i++) {         
		for (int j = 0; j < 3; j++) {             
			cout << C[i][j] << " ";         
		}         
		cout << endl;     
	}      
	return 0; 
}
```

---

## 7. Applications of Matrix Multiplication

- 🎨 Computer graphics and image processing
- 📐 Solving systems of linear equations
- 🤖 Machine learning and neural networks
- 🔐 Cryptography and secure communications