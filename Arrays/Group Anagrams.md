# 49. Group Anagrams

## Problem

**LeetCode Link:** https://leetcode.com/problems/group-anagrams/

---

## Approach

Use a hash map to group words that have the same sorted representation.

### Key Observation

All anagrams have the same characters when sorted.

Example:

```text
eat -> aet
tea -> aet
ate -> aet
```

Use the sorted string as the key and store all matching words in a list.

---

## Solution (Python)

```python
class Solution:
    def sorting(self,strs):
        strs = list(strs)
        strs.sort()
        return "".join(strs)
    def groupAnagrams(self, strs):
        ans = {}
        for string in strs:
            keys = self.sorting(string)
            if keys in ans:
                ans[keys].append(string)
            else:
                ans[keys] = [string]
        return list(ans.values())
```

---

## Complexity Analysis

### Time Complexity

- O(n × k log k)

Where:

- n = number of strings
- k = maximum length of a string

Sorting each string takes O(k log k).

### Space Complexity

- O(n × k)

For storing the grouped anagrams.

---

## Concepts Used

- Hash Map
- Strings
- Sorting

---
