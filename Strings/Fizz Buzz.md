# 412. Fizz Buzz

## Problem

Given an integer `n`, return a string array `answer` (1-indexed) where:

- `answer[i] == "FizzBuzz"` if `i` is divisible by both 3 and 5.
- `answer[i] == "Fizz"` if `i` is divisible by 3.
- `answer[i] == "Buzz"` if `i` is divisible by 5.
- `answer[i] == str(i)` if none of the above conditions are true.
  
**LeetCode Link:** https://leetcode.com/problems/fizz-buzz/

---

## Approach

Iterate from `1` to `n`.

For each number:

1. Check if it is divisible by both `3` and `5`.
2. Check if it is divisible by `3`.
3. Check if it is divisible by `5`.
4. Otherwise, add the number as a string.

---

## Solution (Python)

```python
class Solution:
    def fizzBuzz(self, n):
        result = []

        for i in range(1, n + 1):

            if i % 15 == 0:
                result.append("FizzBuzz")

            elif i % 3 == 0:
                result.append("Fizz")

            elif i % 5 == 0:
                result.append("Buzz")

            else:
                result.append(str(i))

        return result
```

---

## Complexity Analysis

### Time Complexity

```text
O(n)
```

We process each number once.

### Space Complexity

```text
O(n)
```

The output array stores `n` strings.

---

## Example

### Input

```text
n = 15
```

### Output

```text
[
 "1",
 "2",
 "Fizz",
 "4",
 "Buzz",
 "Fizz",
 "7",
 "8",
 "Fizz",
 "Buzz",
 "11",
 "Fizz",
 "13",
 "14",
 "FizzBuzz"
]
```

---

## Concepts Used

- Loops
- Modulo Operator
- Conditional Statements
- String Manipulation

---

