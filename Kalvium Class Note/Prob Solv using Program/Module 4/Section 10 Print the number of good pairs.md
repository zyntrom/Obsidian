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
using namespace std;

int main() {
    int n;
    cin >> n;
    int arr[n];
    for (int i = 0; i < n; i++) cin >> arr[i];
    long long goodPairs = 0;
    for (int i = 0; i < n; i++) {
        for (int j = i + 1; j < n; j++) {
            if (arr[i] == arr[j]) {
                goodPairs++;
            }
        }
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
good_pairs = 0

for i in range(n):
    for j in range(i + 1, n):
        if arr[i] == arr[j]:
            good_pairs += 1

print(good_pairs)
```

---

## 🔹 Java Solution

```java
import java.util.Scanner;

public class GoodPairs {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[] arr = new int[n];
        for (int i = 0; i < n; i++) {
            arr[i] = sc.nextInt();
        }
        long goodPairs = 0;
        for (int i = 0; i < n; i++) {
            for (int j = i + 1; j < n; j++) {
                if (arr[i] == arr[j]) {
                    goodPairs++;
                }
            }
        }
        System.out.println(goodPairs);
    }
}
```

---

✅ **Efficient**: O(n)  
✅ **Works for large inputs**  
✅ **Same formula across C++ / Python / Java**