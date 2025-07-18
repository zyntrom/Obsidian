## 🧩 Arrays

### 🟦 C++

```c++
// C++ Array Functions (for primitive arrays) 
sizeof(arr)          // Size in bytes 
sizeof(arr)/sizeof(arr[0]) // Number of elements  // For 
std::vector (dynamic array) v.size()             // Number of elements 
v.push_back(x)       // Add element at end 
v.pop_back()         // Remove last 
v.clear()            // Remove all 
v.empty()            // Check if empty 
v[i]                 // Access element 
v.front(), v.back()  // First, last element 
v.insert(pos, x)     // Insert at pos 
v.erase(pos)         // Remove at pos 
std::sort(v.begin(), v.end()) // Sort 
std::reverse(v.begin(), v.end()) // Reverse 
std::find(v.begin(), v.end(), x) // Find element
```