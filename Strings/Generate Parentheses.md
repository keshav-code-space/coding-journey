# 22. Generate Parentheses

## Problem

Given `n` pairs of parentheses, write a function to generate all combinations of well-formed parentheses.

**LeetCode Link:** https://leetcode.com/problems/generate-parentheses/

---

## Approach: Backtracking

### Key Idea

At any point:

- We can add `'('` if we still have opening brackets available.
- We can add `')'` only if the number of closing brackets used is less than the number of opening brackets used.

This guarantees that every generated string is valid.

---

## Solution

```python
class Solution:
    def generateParenthesis(self, n):

        ans = []

        def backtrack(curr, open_count, close_count):

            if len(curr) == 2 * n:
                ans.append(curr)
                return

            if open_count < n:
                backtrack(
                    curr + "(",
                    open_count + 1,
                    close_count
                )

            if close_count < open_count:
                backtrack(
                    curr + ")",
                    open_count,
                    close_count + 1
                )

        backtrack("", 0, 0)

        return ans
```
## Complexity Analysis

### Time Complexity

```text
O(4^n / √n)
```

The number of valid combinations is the nth Catalan Number.

Approximation:

```text
Catalan(n) ≈ 4^n / (n^(3/2))
```

So the overall complexity is:

```text
O(4^n / √n)
```

---

### Space Complexity

```text
O(n)
```

Recursive call stack depth.

(Not counting the output list.)

---

## Example 1

### Input

```text
n = 3
```

### Output

```text
[
 "((()))",
 "(()())",
 "(())()",
 "()(())",
 "()()()"
]
```

---

## Concepts Used

- Recursion
- Backtracking
- Decision Tree
- String Construction
- Catalan Numbers

---
