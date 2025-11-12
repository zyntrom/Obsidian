# 📒 Notes: First Non-Repeating Character in a Stream

---

## 🔹 Problem Statement

Given a **stream of characters**, for each new character added, **output the first non-repeating character** seen so far.

- If no non-repeating character exists at any point → output `-1`
- Must **maintain order** → use a **queue**
- Use a **frequency map** to track occurrences

**Input:**

- Single line: space-separated characters
- `1 ≤ |S| ≤ 1000`

**Output:**

- For each character added, print the **first non-repeating character** or `-1`

---

### Example 1

**Input:**

```
a a b c b
```

**Output:**

```
a -1 a a c
```

**Explanation:**

- Step 1: Stream: `a` → first non-repeating: `a`
- Step 2: Stream: `a a` → all repeated → `-1`
- Step 3: Stream: `a a b` → first non-repeating: `b`
- Step 4: Stream: `a a b c` → first non-repeating: `b`
- Step 5: Stream: `a a b c b` → first non-repeating: `c`

---

### Example 2

**Input:**

```
x y x y z
```

**Output:**

```
x x y y z
```

---

## 🔹 Approach

**Use a queue + frequency map**
1. **Initialize:**
    - `queue` → stores characters in order of appearance
    - `freq_map` → stores frequency of each character
2. **Process each character:**
    - Increment its count in `freq_map`
    - Enqueue it into `queue`
3. **Check queue for first non-repeating:**
    - While `queue` is not empty:
        - Check the front character
        - If `freq[front] == 1` → this is the first non-repeating character → output it
        - Else → dequeue front character (it is repeating)
    - If queue becomes empty → output `-1`

**Edge Case:**

- Empty input → output `-1`

**Time Complexity:** `O(N)`  
**Space Complexity:** `O(N)`

---

## 🔹 Code Implementations

### ✅ Python Implementation

```python
from collections import deque, defaultdict

stream = input().split()
if not stream or stream == ['']:
    print(-1)
else:
    queue = deque()
    freq = defaultdict(int)
    
    for ch in stream:
        freq[ch] += 1
        queue.append(ch)
        
        # Remove repeating characters from front
        while queue and freq[queue[0]] > 1:
            queue.popleft()
        
        if queue:
            print(queue[0], end=" ")
        else:
            print(-1, end=" ")

```
---

### ✅ Java Implementation

```java
import java.util.*;
public class FirstNonRepeatingChar {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String[] stream = sc.nextLine().split(" ");
        if (stream.length == 0 || (stream.length == 1 && stream[0].equals(""))) {
            System.out.println(-1);
            return;
        }
        
        Queue<String> queue = new LinkedList<>();
        Map<String, Integer> freq = new HashMap<>();
        
        for (String ch : stream) {
            freq.put(ch, freq.getOrDefault(ch, 0) + 1);
            queue.add(ch);
            
            while (!queue.isEmpty() && freq.get(queue.peek()) > 1) {
                queue.poll();
            }
            
            if (!queue.isEmpty()) System.out.print(queue.peek() + " ");
            else System.out.print("-1 ");
        }
    }
}

```
---

### ✅ C++ Implementation

```cpp
#include <iostream>
#include <queue>
#include <unordered_map>
using namespace std;

int main() {
    string input;
    getline(cin, input);
    
    if (input.empty() || input == " ") {
        cout << -1;
        return 0;
    }
    
    queue<char> q;
    unordered_map<char,int> freq;
    
    for (char ch : input) {
        if (ch == ' ') continue; // skip spaces
        freq[ch]++;
        q.push(ch);
        
        while (!q.empty() && freq[q.front()] > 1)
            q.pop();
        
        if (!q.empty()) cout << q.front() << " ";
        else cout << -1 << " ";
    }
}

```

---

## 🔹 Key Takeaways

- **Queue** maintains order of characters → first non-repeating
- **Hash map** tracks frequency efficiently → O(1) access
- **Pop from queue** front until a non-repeating character is found
- Handles **edge cases**: empty input or all repeating characters
- **Time Complexity:** `O(N)`
- **Space Complexity:** `O(N)`