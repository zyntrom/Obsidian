### 🐍 Python Code – Factors of a Number

```python
n = int(input())  
for i in range(1, n + 1):     
	if n % i == 0:         
		print(i, end=",")
```

---
	
### 💠 C++ Code – Factors of a Number

```c++
#include <iostream> 
using namespace std;  
int main() {     
	int n;     
	cin >> n;      
	for (int i = 1; i <= n; i++) {         
		if (n % i == 0) {             
			cout << i << ",";         
		}     
	}      
	return 0; 
}
```