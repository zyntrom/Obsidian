# 📝 Notes on Good Pairs

## 🔹 Definition

- A **good pair** is a pair `(i, j)` such that:
    1. `arr[i] == arr[j]`
    2. `i != j` (different positions).

## 🔹 Example

Input: `[1, 2, 3, 2, 1]`
- Pairs:
    - `(1, 1)` → indices (0, 4) ✅
    - `(2, 2)` → indices (1, 3) ✅
- Total = `2` good pairs.

Output: `2`

---

## 🔹 Concept Used

- Count frequency of each element.
- For each element with frequency `f`:
    - Number of good pairs = `f * (f - 1) / 2`
    - Because that’s the formula for **choosing 2 identical items**.

---

## 🔹 Algorithm (Efficient Way)

1. Input array.
2. Count frequency of each element.
3. For each frequency `f`: add `f * (f - 1) / 2` to answer.
4. Print answer.

---

# 🖥️ Solutions

---

## 🔹 C++ Solution

```cpp
#include <iostream>
#include <unordered_map>
using namespace std;

int main() {
    int n;
    cin >> n;
    int arr[n];
    
    for (int i = 0; i < n; i++) {
        cin >> arr[i];
    }
    unordered_map<int, int> freq;
    for (int i = 0; i < n; i++) {
        freq[arr[i]]++;
    }
    long long goodPairs = 0;
    for (auto it : freq) {
        int f = it.second;
        goodPairs += (long long)f * (f - 1) / 2;
    }
    cout << goodPairs << endl;
    return 0;
}

```
---

## 🔹 Python Solution

```python
n = int(input())
arr = list(map(int, input().split()))

freq = {}
for num in arr:
    freq[num] = freq.get(num, 0) + 1

good_pairs = 0
for f in freq.values():
    good_pairs += f * (f - 1) // 2

print(good_pairs)

```

---

## 🔹 Java Solution

```java
import java.util.*;

public class GoodPairs {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[] arr = new int[n];
        for (int i = 0; i < n; i++) {
            arr[i] = sc.nextInt();
        }
        HashMap<Integer, Integer> freq = new HashMap<>();
        for (int num : arr) {
            freq.put(num, freq.getOrDefault(num, 0) + 1);
        }
        long goodPairs = 0;
        for (int f : freq.values()) {
            goodPairs += (long) f * (f - 1) / 2;
        }
        System.out.println(goodPairs);
        sc.close();
    }
}

```

---

✅ **Efficient**: O(n)  
✅ **Works for large inputs**  
✅ **Same formula across C++ / Python / Java**