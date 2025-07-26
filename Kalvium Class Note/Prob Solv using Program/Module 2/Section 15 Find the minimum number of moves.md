### ✅ **Logic and Explanation (Approach)**

We are allowed to either:

- Add any number from 1 to 10 to `a`, OR
- Subtract any number from 1 to 10 from `a`, in one move.

So, to find how many such moves it takes to reach `b` from `a`:

- Find the **absolute difference** between `a` and `b`:  
    `diff = abs(a - b)`
- In one move, the **maximum change** is 10.  
    So the minimum moves required will be:  
    `moves = diff / 10`, rounded up (i.e., ceiling).

Use `ceil(diff / 10.0)` for that.

---

### ✅ **C++ Code**

```c++
#include <iostream> 
#include <cmath> // for abs and ceil 
using namespace std;  
int main() {     
	int a, b;     
	cin >> a >> b;      
	int diff = abs(a - b);     
	int moves = (diff + 9) / 10; // same as 
	ceil(diff / 10.0)      
	cout << moves << endl;     
	return 0; 
}
```

---

### ✅ **Python Code**


```python
import math  
a, b = map(int, input().split())  
diff = abs(a - b) 
moves = math.ceil(diff / 10)  
print(moves)
```