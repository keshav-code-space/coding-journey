# 20. Valid Parentheses

## Problem

**LeetCode Link:** https://leetcode.com/problems/valid-parentheses/

---

## Approach

Use a Stack.

### Key Idea

- Push opening brackets onto the stack.
- When a closing bracket appears:
  - Check if the stack is empty.
  - Check whether the top element matches the corresponding opening bracket.
- If not, return `False`.
- At the end, the stack must be empty.

---

## Solution (Python)

```python
class Solution:
    def isValid(self, s):
        stack = []

        pairs = {
            ')': '(',
            '}': '{',
            ']': '['
        }

        for ch in s:

            if ch in pairs:
                if not stack or stack[-1] != pairs[ch]:
                    return False

                stack.pop()

            else:
                stack.append(ch)

        return len(stack) == 0
```

---

## Complexity Analysis

### Time Complexity

- O(n)

Each character is pushed and popped at most once.

### Space Complexity

- O(n)

In the worst case, all characters are opening brackets.

---

## Example 1

### Input

```text
s = "()"
```

### Output

```text
True
```

---

## Concepts Used

- Stack
- String Processing
- Matching Pairs

---

