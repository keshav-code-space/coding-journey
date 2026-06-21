# 844. Backspace String Compare

## Problem

Given two strings `s` and `t`, return `true` if they are equal when both are typed into empty text editors.

`#` means a backspace character.

**LeetCode Link:** https://leetcode.com/problems/backspace-string-compare/

---

## Approach 1: Stack

### Idea

Simulate typing in a text editor.

- Character → push to stack
- `#` → pop from stack (if not empty)

Compare the final strings.

---

## Solution

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

            return ''.join(stack)

        return build(s) == build(t)
```

---

## Complexity

### Time Complexity

```text
O(n + m)
```

### Space Complexity

```text
O(n + m)
```

---

## Approach 2: Two Pointers (Optimal)

### Idea

Traverse both strings from right to left.

- Count backspaces using skip counters.
- Skip deleted characters.
- Compare valid characters.

---

## Solution

```python
class Solution:
    def backspaceCompare(self, s, t):

        i = len(s) - 1
        j = len(t) - 1

        skipS = 0
        skipT = 0

        while i >= 0 or j >= 0:

            while i >= 0:
                if s[i] == '#':
                    skipS += 1
                    i -= 1
                elif skipS:
                    skipS -= 1
                    i -= 1
                else:
                    break

            while j >= 0:
                if t[j] == '#':
                    skipT += 1
                    j -= 1
                elif skipT:
                    skipT -= 1
                    j -= 1
                else:
                    break

            if i >= 0 and j >= 0:
                if s[i] != t[j]:
                    return False
            elif i >= 0 or j >= 0:
                return False

            i -= 1
            j -= 1

        return True
```

---

## Complexity

### Time Complexity

```text
O(n + m)
```

### Space Complexity

```text
O(1)
```

---

## Example

### Input

```text
s = "ab#c"
t = "ad#c"
```

### Process

```text
ab#c -> ac
ad#c -> ac
```

### Output

```text
True
```

---

## Concepts Used

- Stack
- Two Pointers
- String Traversal
- String Simulation
- Reverse Traversal
- Space Optimization

---
