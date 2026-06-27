# 49. Group Anagrams

## Problem

Given an array of strings `strs`, group the anagrams together.

You can return the answer in any order.

An **Anagram** is a word or phrase formed by rearranging the letters of another word using all the original letters exactly once.

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
from collections import defaultdict

class Solution:
    def groupAnagrams(self, strs):
        groups = defaultdict(list)

        for word in strs:
            key = "".join(sorted(word))
            groups[key].append(word)

        return list(groups.values())
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

## Example

### Input

```text
strs = ["eat","tea","tan","ate","nat","bat"]
```

### Output

```text
[
    ["eat","tea","ate"],
    ["tan","nat"],
    ["bat"]
]
```

---

## Concepts Used

- Hash Map
- Strings
- Sorting
- Grouping

