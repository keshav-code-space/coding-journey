# Factorial

## Problem Statement

Given a non-negative integer `n`, return the factorial of `n`.

The factorial of a number is the product of all positive integers less than or equal to that number.

Mathematically:

n! = n × (n - 1) × (n - 2) × ... × 2 × 1

Special Case:

```text
0! = 1
```

---

# Approach 1: Recursion

## Idea

Factorial follows a recursive pattern:

```text
n! = n × (n - 1)!
```

Keep multiplying until reaching the base case.

---

## Solution

```python
def factorial(n):

    if n == 0 or n == 1:
        return 1

    return n * factorial(n - 1)
```

---

## Complexity Analysis

### Time Complexity

```text
O(n)
```

One recursive call for each number.

### Space Complexity

```text
O(n)
```

---

## Example 1

### Input

```text
n = 5
```

### Output

```text
120
```

### Explanation

```text
5! = 5 × 4 × 3 × 2 × 1
   = 120
```

---

## Concepts Used

- Recursion
- Iteration
- Mathematics
- Multiplication Pattern
