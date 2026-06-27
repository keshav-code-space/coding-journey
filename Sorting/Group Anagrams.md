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
