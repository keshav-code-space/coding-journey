# 844. Backspace String Compare

## Problem

**LeetCode Link:** https://leetcode.com/problems/backspace-string-compare/

---

## Approach 1: Stack Simulation

### Idea

Simulate typing into a text editor.

- If the character is not `#`, push it onto the stack.
- If the character is `#`, remove the most recent character (if any).
- Compare the final strings.

---

## Solution (Python)

```python
class Solution:
    def backspaceCompare(self, s, t):

        def build(string):
            stack = []

            for ch in string:

                if ch != '#':
                    stack.append(ch)

                elif stack:
                    stack.pop()

            return "".join(stack)

        return build(s) == build(t)
```

---

## Complexity Analysis

### Time Complexity

```text
O(n + m)
```

Where:

- n = length of s
- m = length of t

### Space Complexity

```text
O(n + m)
```

Stacks store the processed strings.

---

## Example 1

### Input

```text
s = "ab#c"
t = "ad#c"
```

Process:

```text
s -> "ac"
t -> "ac"
```

Output:

```text
True
```

---

## Concepts Used

- Stack
- Two Pointers
- String Simulation

---
