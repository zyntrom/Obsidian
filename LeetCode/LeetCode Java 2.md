## 11. Length of Last Word

```java
class Solution {
public:
    int lengthOfLastWord(string s) {
        int n = s.length();
        int count = 0;
        int p = n - 1;
        for (int i = 0; i < n; i++) {
            if (s[i] != ' ') {
                p = i;
            }
        }
        for (int i = p; i >= 0; i--) {
            if (s[i] == ' ') {
                break;
            }
            count++;
        }
        return count;
    }
};

```

## 12. Plus One

```java

```
