# Matrix Operations – Notes

## 1. Matrix Transpose

- Definition: The transpose of a matrix **A** is another matrix **AT** obtained by flipping rows and columns.
- Formula:  
    AT[j][i] = A[i][j]

### Example:

If  
A =  
[ 1 2 3 ]  
[ 4 5 6 ]

Then  
AT =  
[ 1 4 ]  
[ 2 5 ]  
[ 3 6 ]

### Code Examples

**C**

```c
for (i = 0; i < rows; i++) {     
	for (j = 0; j < cols; j++) {         
		AT[j][i] = A[i][j];     
	} 
}
```

**C++**

```c++
for (int i = 0; i < rows; i++) {     
	for (int j = 0; j < cols; j++) {         
		AT[j][i] = A[i][j];     
	} 
}
```

**Java**

```java
for (int i = 0; i < rows; i++) {     
	for (int j = 0; j < cols; j++) {         
		AT[j][i] = A[i][j];     
	} 
}
```

**Python**

```python
for i in range(rows):     
	for j in range(cols):         
		AT[j][i] = A[i][j]
```

---

## 2. Scalar Multiplication of a Matrix

- Definition: Multiplying every element of a matrix **A** by a scalar value **s** produces a new matrix **C**.
- Formula:  
    C[i][j] = s * A[i][j]

### Example:

If  
s = 3  
A =  
[ 1 2 ]  
[ 3 4 ]

Then  
C =  
[ 3 6 ]  
[ 9 12 ]

### Code Examples

**C**

```c
for (i = 0; i < rows; i++) {     
	for (j = 0; j < cols; j++) {         
		C[i][j] = s * A[i][j];     
	} 
}
```

**C++**

```c++
for (int i = 0; i < rows; i++) {     
	for (int j = 0; j < cols; j++) {         
		C[i][j] = s * A[i][j];     
	} 
}
```

**Java**

```java
for (int i = 0; i < rows; i++) {     
	for (int j = 0; j < cols; j++) {         
		C[i][j] = s * A[i][j];     
	} 
}
```

**Python**

```python
for i in range(rows):     
	for j in range(cols):         
		C[i][j] = s * A[i][j]
```