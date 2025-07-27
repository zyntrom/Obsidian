### ✅ **C Program: Longest Increasing Contiguous Subsequence**

```c
#include <stdio.h>  
int main() {     
	int prev, curr;     
	int len = 0;      // Current increasing subsequence length     
	int maxlen = 0;   // Longest subsequence length      
	// Read the first number     
	scanf("%d", &prev);      
	// Check for empty input (first number is -1)     
	if (prev == -1) {         
		printf("0\n");         
		return 0;     
	}      
	len = 1;        // We have at least one number     
	maxlen = 1;      // Read numbers until -1 is encountered     
	while (1) {         
		scanf("%d", &curr);          
		if (curr == -1) {             
			break;         
		}          
		if (curr > prev) {             
		// Increasing, so extend the current sequence             
			len++;         
		} 
		else {             
		// Not increasing, so reset the length             
			len = 1;         
		}          
		// Update maxlen if current sequence is longer         
		if (len > maxlen) {             
			maxlen = len;         
		}          
		// Advance prev to current         
		prev = curr;     
	}      
	printf("%d\n", maxlen);      
	return 0; 
}
```

---

### 🧪 **Sample Runs**

#### **Example 1**:

**Input**:  
```
9 2 4 0 3 4 6 9 2 -1  
```
**Output**:  
```
5
```

#### **Example 2**:

**Input**:  
```
11 9 7 8 11 12 15 15 -1  
```
**Output**:  
```
`5`
```

#### **Example 3**:

**Input**:  
```
5 -1  
```
**Output**:  
```
1
```

#### **Example 4**:

**Input**:  
```
-1  
```
**Output**:  
```
0
```

---

### ✅ **Explanation of Key Parts**

- `scanf("%d", &prev);` reads the first number.
- If it's `-1`, we immediately exit since there's no sequence.
- The loop reads each subsequent number.
- We compare `curr` with `prev`:
    - If `curr > prev`: the sequence is increasing → `len++`.
    - Else → reset `len = 1`.
- After every update, we check if the `len` is greater than `maxlen` and update accordingly.
- After the loop ends, we print `maxlen`.

---

### 📌 Summary of What Was Added

Compared to earlier versions:

- Introduced and used `maxlen` properly.
- Handled edge case: input starts directly with `-1`.
- Clean advancement of `prev` to `curr`.
- Handled very short sequences (1 or 0 elements) correctly.