# 17. Letter Combinations of a Phone Number

## Problem

Given a string containing digits from `2-9` inclusive, return all possible letter combinations that the number could represent.

Return the answer in any order.

The mapping is the same as on telephone buttons:

```text
2 -> abc
3 -> def
4 -> ghi
5 -> jkl
6 -> mno
7 -> pqrs
8 -> tuv
9 -> wxyz
```


**LeetCode Link:** https://leetcode.com/problems/letter-combinations-of-a-phone-number/

---

## Approach

Use Recusion.

For each digit:

1. Get the corresponding letters.
2. Make the recursive call for the next subarray to give the result.
3. Using the loop iterate in the `self.dict` for the first element and for the rest as well.

Build combinations until the length of the current combination equals the length of the input digits.

---

## Solution (Python)

```python
class Solution:
    def __init__(self):
        self.dict = {"1":"", "2":"abc", "3":"def", "4":"ghi", "5":"jkl", "6":"mno", "7":"pqrs", "8":"tuv","9":"wxyz"}
    def letterCombinations(self, digits: str) -> List[str]:
        if digits == "":
            return [""]
        ans=[]
        smallPart = digits[1:]
        smallPartWord = self.letterCombinations(smallPart)

        keyletter = self.dict[digits[0]]

        for word in keyletter:
            for value in smallPartWord :
                ans.append(word+value)
        return ans
```

---

## Complexity Analysis

### Time Complexity

- O(4ⁿ)

Where `n` is the number of digits.

Each digit can contribute up to 4 possible letters.

### Space Complexity

- O(n)

Recursion stack depth.

---

## Example

### Input

```text
digits = "23"
```

### Output

```text
[
 "ad","ae","af",
 "bd","be","bf",
 "cd","ce","cf"
]
```

---

## Concepts Used

- Recursion
- Backtracking
- DFS
- Combinatorial Search

---
