## 1. Given two strings s and t, return true if t is an anagram of s, and false otherwise

- Anagram basically occurs when all letters are present in both strings. Example: cat and tac , abc and cab.
- The length of both the numbers are same in an anagram.

Since the alphabet has only 26 letters we can just use an array for this question. Hashmap is also appropriate for this.


```python
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        if len(s) != len(t):
            return False

        # create array to count char frequencies
        char_counts = [0] * 26

        for i in range(len(s)):
            char_counts[ord(s[i]) - ord('a')] += 1
            char_counts[ord(t[i]) - ord('a')] -= 1

        for count in char_counts:
            if count != 0:
                return False

        return True
```