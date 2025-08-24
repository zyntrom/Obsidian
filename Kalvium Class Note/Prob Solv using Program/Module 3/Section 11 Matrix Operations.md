# Matrix Operations – Notes

## 1. Matrix Addition

- **Definition**: Add corresponding elements of two matrices of the same size.
- **Formula**:  
    C[i][j] = A[i][j] + B[i][j]

### Example:

A = [ [1, 2], [3, 4] ]  
B = [ [5, 6], [7, 8] ]  
C = [ [6, 8], [10, 12] ]

### Python Code

```python
def matrix_addition(A, B):     
	rows, cols = len(A), len(A[0])     
	C = [[0]*cols for _ in range(rows)]     
	for i in range(rows):         
		for j in range(cols):             
			C[i][j] = A[i][j] + B[i][j]     
	return C
```

### C++ Code

```c++
for (int i = 0; i < rows; i++) {     
	for (int j = 0; j < cols; j++) {         
		C[i][j] = A[i][j] + B[i][j];     
	} 
}
```

---

## 2. Matrix Subtraction

- **Definition**: Subtract corresponding elements of two matrices of the same size.
- **Formula**:  
    C[i][j] = A[i][j] - B[i][j]

### Example:

A = [ [9, 7], [6, 4] ]  
B = [ [5, 6], [2, 3] ]  
C = [ [4, 1], [4, 1] ]

### Python Code

```python
def matrix_subtraction(A, B):     
	rows, cols = len(A), len(A[0])     
	C = [[0]*cols for _ in range(rows)]     
	for i in range(rows):         
		for j in range(cols):             
			C[i][j] = A[i][j] - B[i][j]     
return C
```

### C++ Code

```c++
for (int i = 0; i < rows; i++) {     
	for (int j = 0; j < cols; j++) {         
		C[i][j] = A[i][j] - B[i][j];     
	} 
}
```

---

## 3. Scalar Multiplication

- **Definition**: Multiply each element of a matrix by a scalar.
- **Formula**:  
    C[i][j] = s * A[i][j]

### Example:

s = 3  
A = [ [1, 2], [3, 4] ]  
C = [ [3, 6], [9, 12] ]

### Python Code

```python
def scalar_multiplication(s, A):     
	rows, cols = len(A), len(A[0])     
		C = [[0]*cols for _ in range(rows)]     
			for i in range(rows):         
				for j in range(cols):             
					C[i][j] = s * A[i][j]     
return C
```

### C++ Code

```c++
for (int i = 0; i < rows; i++) {     
	for (int j = 0; j < cols; j++) {         
		C[i][j] = s * A[i][j];     
	} 
}
```

---

## 4. Matrix Transpose

- **Definition**: Flip a matrix over its diagonal → rows become columns.
- **Formula**:  
    AT[j][i] = A[i][j]

### Example:

A = [ [1, 2, 3], [4, 5, 6] ]  
AT = [ [1, 4], [2, 5], [3, 6] ]

### Python Code

```python
def matrix_transpose(A):     
	rows, cols = len(A), len(A[0])     
	AT = [[0]*rows for _ in range(cols)]     
	for i in range(rows):         
		for j in range(cols):             
			AT[j][i] = A[i][j]     
return AT
```

### C++ Code

```c++
for (int i = 0; i < rows; i++) {     
	for (int j = 0; j < cols; j++) {         
		AT[j][i] = A[i][j];     
	} 
}
```

---

## 5. Diagonal Sum (Square Matrix)

- **Definition**: Sum of elements on primary and secondary diagonals.
- **Formulas**:  
    Primary diagonal → A[i][i]  
    Secondary diagonal → A[i][n - i - 1]

### Example:

A =  
[ [1, 2, 3],  
[ 4, 5, 6 ],  
[7, 8, 9] ]

Primary = 1 + 5 + 9 = 15  
Secondary = 3 + 5 + 7 = 15

### Python Code

```python
def diagonal_sum(A):     
	n = len(A)     
	primary = sum(A[i][i] 
	for i in range(n)):     
		secondary = sum(A[i][n-i-1] 
		for i in range(n))     
return primary, secondary
```

### C++ Code

```c++
int primary = 0, secondary = 0; 
for (int i = 0; i < n; i++) {     
	primary += A[i][i];     
	secondary += A[i][n - i - 1]; 
}

```