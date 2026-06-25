# 5. Longest Palindromic Substring

## Problem

Given a string `s`, return the longest palindromic substring in `s`.

A palindrome reads the same forward and backward.

**LeetCode Link:** https://leetcode.com/problems/longest-palindromic-substring/

---

## Approach: Expand Around Center

### Key Idea

Every palindrome has a center.

For each index:

- Expand considering it as the center of an odd-length palindrome.
- Expand considering it as the center of an even-length palindrome.
- Keep track of the longest palindrome found.

---

## Solution

```python
class Solution(object):
    def longestPalindrome(self, s):
        n = len(s)
        ans = ""
        for i in range(n):
            start = end = i

            while start >=0 and end <n and s[start] == s[end]:
                start -=1
                end +=1
            temp = s[start+1:end]
            if len(temp) > len(ans):
                ans = temp
            
            start = i
            end = i+1
            while start >=0 and end <n and s[start] == s[end]:
                start -=1
                end +=1
            temp = s[start+1:end]
            if len(temp) > len(ans):
                ans = temp
        return ans

```

---

## Complexity Analysis

### Time Complexity

```text
O(n²)
```

For each character, expansion can take O(n).

---

### Space Complexity

```text
O(1)
```

No extra data structures are used.

---

## Example 1

### Input

```text
s = "babad"
```

### Output

```text
"bab"
```

or

```text
"aba"
```

Both are valid.

---

## Concepts Used

- Two Pointers
- String Traversal
- Expand Around Center
- Palindrome Checking

---
