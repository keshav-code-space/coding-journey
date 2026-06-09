# 20. Valid Parentheses

## Problem

**LeetCode Link:** https://leetcode.com/problems/valid-parentheses/


---

## Approach: Stack

### Key Observation

Whenever we see an opening bracket:

```text
(  {  [
```

we need to remember it until its matching closing bracket appears.

A **Stack** is perfect because:

```text
Last Opened → First Closed
```

(LIFO)

---

## Solution (Python)

```python
class Solution:
    def isValid(self, s):

        stack = []

        mapping = {
            ')': '(',
            '}': '{',
            ']': '['
        }

        for ch in s:

            if ch in "([{":
                stack.append(ch)

            else:

                if not stack:
                    return False

                if stack.pop() != mapping[ch]:
                    return False

        return len(stack) == 0
```

---

## Complexity Analysis

### Time Complexity

```text
O(n)
```

Each bracket is pushed and popped at most once.

### Space Complexity

```text
O(n)
```

In the worst case:

```text
(((((((
```

all brackets are stored in the stack.

---

## Why Does Stack Work?

Consider:

```text
([{}])
```

The most recently opened bracket:

```text
{
```

must be closed first.

This is exactly:

```text
Last In First Out (LIFO)
```

which is the behavior of a stack.

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
- String Traversal
- Hash Map

---
