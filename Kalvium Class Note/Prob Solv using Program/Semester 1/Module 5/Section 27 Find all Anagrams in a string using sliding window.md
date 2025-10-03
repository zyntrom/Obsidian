# 📒 5.27 Find All Anagrams in a String Using Sliding Window

---

## 🔹 Problem Statement

Given:

- `text` → a string of lowercase characters
- `pattern` → a string whose anagrams we need to find

Task: Count **all substrings in `text` that are anagrams of `pattern`** using **sliding window technique**.

**Output:** Count of such substrings

---

## 🔹 Example

**Example 1:**

```
Input: text = "forxxorfxdofr" pattern = "for"  
Output: 3
```

- Anagrams in text: "for", "orf", "ofr"

**Example 2:**

```
Input: text = "aabaabaa" pattern = "aaba"  
Output: 4
```

- Anagrams in text: "aaba", "abaa", "aaba", "abaa"

---

## 🔹 Approach Using Sliding Window

1. **Frequency Maps:**
    - Create a frequency map (`dict`) for the `pattern`.
    - Maintain a frequency map for the current **window of size = len(pattern)** in `text`.
2. **Initialize Sliding Window:**
    - Start with the first `len(pattern)` characters in `text`.
3. **Slide and Compare:**
    - Slide the window one character at a time:
        - Remove frequency of the character leaving the window
        - Add frequency of the new character entering the window
    - Compare the window’s frequency map with the pattern’s frequency map
        - If equal → increment count
4. **Return Count:**
    - Total number of anagram substrings

---

## 🔹 Python Implementation

```python
from collections import Counter

text = input().strip()
pattern = input().strip()

k = len(pattern)
pattern_count = Counter(pattern)
window_count = Counter(text[:k])

count = 0
if window_count == pattern_count:
    count += 1

for i in range(k, len(text)):
    start_char = text[i - k]
    end_char = text[i]

    # Remove start_char from window
    window_count[start_char] -= 1
    if window_count[start_char] == 0:
        del window_count[start_char]

    # Add end_char to window
    window_count[end_char] += 1

    # Compare window with pattern
    if window_count == pattern_count:
        count += 1

print(count)

```

---

## 🔹 C++ Implementation

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    string text, pattern;
    cin >> text >> pattern;

    int k = pattern.size();
    unordered_map<char,int> p_count, w_count;

    for(char c : pattern) p_count[c]++;
    for(int i = 0; i < k; i++) w_count[text[i]]++;

    int count = 0;
    if(w_count == p_count) count++;

    for(int i = k; i < text.size(); i++){
        char start_char = text[i-k];
        char end_char = text[i];

        w_count[end_char]++;
        w_count[start_char]--;
        if(w_count[start_char] == 0) w_count.erase(start_char);

        if(w_count == p_count) count++;
    }

    cout << count << endl;
    return 0;
}

```

---

## 🔹 Java Implementation

```java
import java.util.*;

public class AnagramCount {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String text = sc.next();
        String pattern = sc.next();

        int k = pattern.length();
        int count = 0;

        int[] p_count = new int[26];
        int[] w_count = new int[26];

        for(char c : pattern.toCharArray()) p_count[c-'a']++;
        for(int i=0; i<k; i++) w_count[text.charAt(i)-'a']++;

        if(Arrays.equals(p_count, w_count)) count++;

        for(int i=k; i<text.length(); i++){
            w_count[text.charAt(i)-'a']++;
            w_count[text.charAt(i-k)-'a']--;
            if(Arrays.equals(p_count, w_count)) count++;
        }

        System.out.println(count);
    }
}

```

---

## 🔹 Complexity Analysis

- **Time Complexity:** O(N × 26) ≈ O(N) for lowercase letters comparison
- **Space Complexity:** O(26) ≈ O(1) → fixed frequency arrays/dictionaries

---

## 🔹 Key Takeaways

- Sliding window avoids recalculating frequency of each substring from scratch
- Efficient for substring anagram problems
- Can be extended for **all character sets** by changing the frequency array/dictionary size