## 📘 1. **Basic Syntax**

### Headers & Main Function

```c++
#include <iostream> 
using namespace std;  
int main() {     
	// code     
	return 0; 
}
```

### Input/Output

```c++
cin >> var;           // input 
cout << var << endl;  // output
```

### Variables & Data Types

```c++
int, float, double, char, bool; long, long long, unsigned int;
```

### Constants

```c++
const int x = 10; 
#define PI 3.14
```

### Conditionals
```c++
if (condition) { 

} 
else if () { 

} else {
	
} 
switch (var) {     
	case value: break;     
	default: break; 
}
```

### Loops

```c++
for (int i = 0; i < n; i++) { 

} 
while (condition) { 

} do { 

} while (condition);
```

### Functions

```c++
returnType functionName(parameters) {     
	// body     
	return value; 
}
```

---

## 📘 2. **Data Structures**

### Arrays

```c++
int arr[5] = {1, 2, 3, 4, 5}; 
int arr2D[3][3];
```

### Strings

```c++
#include <string> 
string s = "hello"; 
s.length(); 
s.size(); 
s += " world"; 
s.substr(0, 3); 
s.find("lo"); 
s.erase(pos, len);
```

### Vectors

```c++
#include <vector>  
vector<int> v; 
v.push_back(10); 
v.pop_back(); 
v.size();
v.clear(); 
v.begin(); 
v.end();
```

### Pairs

```c++
#include <utility>  
pair<int, int> p = {1, 2}; 
p.first; 
p.second;
```

### Sets

```c++
#include <set>  
set<int> s;
s.insert(5); 
s.erase(5); 
s.count(5); 
s.find(5);
```

### Maps

```c++
#include <map>  
map<string, int> m; 
m["apple"] = 3; 
m.count("apple");
```

### Stack

```c++
#include <stack>  
stack<int> s; s
.push(1); 
s.top(); 
s.pop(); 
s.empty();
```

### Queue

```c++
#include <queue>  
queue<int> q; 
q.push(1); 
q.front(); 
q.back(); 
q.pop();
```

### Priority Queue

```c++
#include <queue>  
priority_queue<int> maxHeap; 
priority_queue<int, vector<int>, greater<int>> minHeap;
```

---

## 📘 3. **Algorithms Library**

```c++
#include <algorithm>
```

### Sorting & Reversing

```c++
sort(v.begin(), v.end()); 
reverse(v.begin(), v.end());
```

### Min/Max

```c++
min(a, b); 
max(a, b);
```

### Accumulate (Sum)

```c++
#include <numeric> 
accumulate(v.begin(), v.end(), 0);
```

### Binary Search


CopyEdit

`binary_search(v.begin(), v.end(), value);`

### Lower/Upper Bound

cpp

CopyEdit

`lower_bound(v.begin(), v.end(), value); upper_bound(v.begin(), v.end(), value);`

### Next Permutation

cpp

CopyEdit

`next_permutation(s.begin(), s.end());`

---

## 📘 4. **Math Functions**

cpp

CopyEdit

`#include <cmath>  sqrt(x);     // Square root pow(x, y);   // x^y abs(x);      // Absolute ceil(x);     // Round up floor(x);    // Round down round(x);    // Nearest integer log(x); log10(x);`

---

## 📘 5. **Time & Random**

cpp

CopyEdit

`#include <ctime> #include <cstdlib>  srand(time(0)); int r = rand() % 100;`

---

## 📘 6. **Useful Macros and Typedefs**

cpp

CopyEdit

`#define fastIO ios::sync_with_stdio(0); cin.tie(0); #define all(x) x.begin(), x.end() typedef long long ll;`

---

## 📘 7. **File I/O**

cpp

CopyEdit

`#include <fstream>  ifstream in("input.txt"); ofstream out("output.txt"); in >> x; out << x;`

---

## 📘 8. **Exception Handling**

cpp

CopyEdit

`try {     // code } catch (exception &e) {     cout << e.what(); }`

---

If you want, I can give: