# Reverse String

## Problem Statement

Given a string `s`, reverse the string and return the reversed result.

---

# Approach 3: Recursion

## Idea

Reverse the remaining string and place the first character at the end.

---

## Solution

```python
def reverseString(s):

    if len(s) <= 1:
        return s

    return reverseString(s[1:]) + s[0]
```

---

