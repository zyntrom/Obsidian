### ✅ Step-by-step Approach

1. **Input Handling**
    - Take 6 integers as input and store them in an array.
2. **Prime Check Function**
    - A number is prime if it is greater than 1 and has no divisors other than 1 and itself.
    - To check efficiently:
        - If number ≤ 1 → Not prime.
        - Check divisibility from 2 to √n.
        - If divisible → Not prime, else prime.
3. **Loop through Array**
    - For each element, check if it’s prime.
    - If yes → increase the counter.
4. **Output the Count**

---

### 🔹 Python Implementation

```python
def is_prime(num):     
	if num <= 1:         
		return False     
	for i in range(2, int(num**0.5) + 1):         
	if num % i == 0:             
		return False     
	return True  
	
# Step 1: Input 
array arr = list(map(int, input().split()))  
# Step 2: 
Count primes prime_count = 0 
for element in arr:     
	if is_prime(element):         
		prime_count += 1  
# Step 3: Output result 
print(prime_count)
```

---

### 🔹 C++ Implementation

```cpp
#include <iostream>
#include <cmath>
using namespace std;

// Function to check if a number is prime
bool isPrime(int num) {
    if (num <= 1) return false;
    for (int i = 2; i <= sqrt(num); i++) {
        if (num % i == 0) return false;
    }
    return true;
}
int main() {
    int arr[6];
    
    // Input array of size 6
    for (int i = 0; i < 6; i++) {
        cin >> arr[i];
    }
    int count = 0;
    // Count prime numbers
    for (int i = 0; i < 6; i++) {
        if (isPrime(arr[i])) {
            count++;
        }
    }
    cout << count << endl;
    return 0;
}
```

---

```embed
title: "L3. Check if a Number if Prime or not | Maths Playlist"
image: "https://i.ytimg.com/vi/MJcckSfoYdI/maxresdefault.jpg"
description: "Check out TUF+:https://takeuforward.org/plus?source=youtubeFind DSA, LLD, OOPs, Core Subjects, 1000+ Premium Questions company wise, Aptitude, SQL, AI doubt ..."
url: "https://youtu.be/MJcckSfoYdI"
favicon: ""
aspectRatio: "56.25"
```

✅ This matches exactly what your assignment requires:

- **Array of size 6**
- **Loop to check prime**
- **Counter for primes**