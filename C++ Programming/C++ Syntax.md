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

## 🔤 Strings

### 🟦 C++

```c++
str.length()            // Length 
str.empty()             // Is empty 
str[i]                  // Access char 
str.substr(pos, len)    // Substring 
str.find("abc")         // Find substring 
str.replace(pos, len, "x") // Replace part 
str.append("abc") str += "abc"            // Add to end 
str.insert(pos, "abc") 
str.erase(pos, len) std::stoi(str), 
std::to_string(num) std::getline(cin, str)  // Input line
```