### 🐍 Python Code – Sum from 1 to `n`:

```python
n = int(input()) 
sum = 0  
for i in range(1, n + 1):     
	sum += i  print(sum)
```

---

### 💠 C++ Code – Sum from 1 to `n`:

```c++
#include <iostream> 
using namespace std;  
int main() {     
	int n;     
	int sum = 0;      
	cin >> n;      
	for (int i = 1; i <= n; i++) {         
		sum += i;     
	}      
	cout << sum;     
	return 0; 
}
```