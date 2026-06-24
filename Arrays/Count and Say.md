# 38. Count and Say

## Problem

The count-and-say sequence is a sequence of digit strings defined recursively.

```text
countAndSay(1) = "1"
```

To generate the next term:

```text
Read off the digits of the previous term.
Count the number of digits and say the digit.
```

**LeetCode Link:** https://leetcode.com/problems/count-and-say/

---

## Approach: String Simulation

### Key Idea

Starting from:

```text
"1"
```

Generate the next string by:

1. Counting consecutive identical digits.
2. Appending:

```text
count + digit
```

to the new string.

Repeat until reaching the nth term.

---

## Recursive Solution

```python
class Solution:
    def countAndSay(self, n):

        if n == 1:
            return "1"

        prev = self.countAndSay(n - 1)

        result = ""
        count = 1

        for i in range(1, len(prev)):

            if prev[i] == prev[i - 1]:
                count += 1

            else:
                result += str(count) + prev[i - 1]
                count = 1

        result += str(count) + prev[-1]

        return result
```

---

## Complexity Analysis

### Time Complexity

```text
O(m)
```

### Space Complexity

```text
O(m + n)
```

Generated string + recursion stack.

---
