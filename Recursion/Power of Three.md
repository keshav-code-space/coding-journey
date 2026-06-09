# 326. Power of Three

## Problem

**LeetCode Link:** https://leetcode.com/problems/power-of-three/

---

## Approach 1: Recursive

### Idea

Keep dividing by 3.

- If we reach 1 → Power of Three.
- If not divisible by 3 → Not a Power of Three.

---

## Solution

```python
class Solution:
    def isPowerOfThree(self, n):

        if n <= 0:
            return False

        if n == 1:
            return True

        if n % 3 != 0:
            return False

        return self.isPowerOfThree(n // 3)
```

---

## Complexity Analysis

### Time Complexity

```text
O(log₃ n)
```

We divide by 3 each recursive call.

### Space Complexity

```text
O(log₃ n)
```

Recursive call stack.

---

## Approach 2: Iterative

### Solution

```python
class Solution:
    def isPowerOfThree(self, n):

        if n <= 0:
            return False

        while n % 3 == 0:
            n //= 3

        return n == 1
```

---

## Complexity Analysis

### Time Complexity

```text
O(log₃ n)
```

### Space Complexity

```text
O(1)
```

---

## Approach 3: Mathematical Trick

### Key Observation

The largest power of 3 within a 32-bit signed integer is:

```text
3^19 = 1162261467
```

Any power of three must divide this number exactly.

---

## Solution

```python
class Solution:
    def isPowerOfThree(self, n):
        return n > 0 and 1162261467 % n == 0
```

---

## Complexity Analysis

### Time Complexity

```text
O(1)
```

### Space Complexity

```text
O(1)
```

---

## Example 1

### Input

```text
n = 27
```

### Output

```text
True
```

### Explanation

```text
27 = 3³
```

---


## Concepts Used

- Recursion
- Mathematics
- Division
- Iteration
- Number Theory

---
