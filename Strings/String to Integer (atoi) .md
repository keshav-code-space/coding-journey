# 8. String to Integer (atoi)

## Problem

Implement the `myAtoi(string s)` function, which converts a string to a 32-bit signed integer.

Rules:

1. Ignore leading whitespace.
2. Check for an optional `+` or `-` sign.
3. Read digits until a non-digit character is encountered.
4. Clamp the result to the 32-bit signed integer range.

**LeetCode Link:** https://leetcode.com/problems/string-to-integer-atoi/

---

## Approach

### Step 1

Skip leading spaces.

```text
"   -42"
   ^
```

---

### Step 2

Check sign.

```text
+
-
```

Default:

```text
sign = +1
```

---

### Step 3

Read digits.

```text
4193abc
```

Read:

```text
4193
```

Stop at:

```text
a
```

---

### Step 4

Handle overflow.

Valid range:

```text
[-2³¹ , 2³¹ - 1]
```

```text
[-2147483648 , 2147483647]
```

---

## Solution

```python
class Solution:
    def myAtoi(self, s):

        i = 0
        n = len(s)

        while i < n and s[i] == ' ':
            i += 1

        sign = 1

        if i < n and s[i] in "+-":

            if s[i] == '-':
                sign = -1

            i += 1

        num = 0

        while i < n and s[i].isdigit():

            num = num * 10 + int(s[i])

            i += 1

        num *= sign

        INT_MIN = -(2 ** 31)
        INT_MAX = (2 ** 31) - 1

        if num < INT_MIN:
            return INT_MIN

        if num > INT_MAX:
            return INT_MAX

        return num
```

---

## Complexity Analysis

### Time Complexity

```text
O(n)
```

Each character is visited at most once.

---

### Space Complexity

```text
O(1)
```

Only a few variables are used.

---

## Example 1

### Input

```text
s = "42"
```

### Output

```text
42
```

---

## Concepts Used

- Strings
- Parsing
- Simulation
- Integer Construction
- Overflow Handling

---

