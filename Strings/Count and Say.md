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

## Solution

```python
class Solution:
    def countAndSay(self, n):

        result = "1"

        for _ in range(n - 1):

            current = ""
            count = 1

            for i in range(1, len(result)):

                if result[i] == result[i - 1]:
                    count += 1

                else:
                    current += str(count)
                    current += result[i - 1]
                    count = 1

            current += str(count)
            current += result[-1]

            result = current

        return result
```

---

## Complexity Analysis

### Time Complexity

```text
O(m)
```

Where:

```text
m = length of the generated nth string
```

Each character is processed once per generation.

---

### Space Complexity

```text
O(m)
```

For storing the generated string.

---

## Example 1

### Input

```text
n = 4
```

### Output

```text
"1211"
```

### Explanation

```text
1      -> one 1      -> 11
11     -> two 1s     -> 21
21     -> one 2 one 1 -> 1211
```

---

## Concepts Used

- String Manipulation
- Simulation
- Recursion
- Consecutive Character Counting

