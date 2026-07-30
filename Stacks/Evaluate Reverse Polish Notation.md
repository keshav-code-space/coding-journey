# 150. Evaluate Reverse Polish Notation

**LeetCode Link:** https://leetcode.com/problems/evaluate-reverse-polish-notation/

---

## Problem Statement

You are given an array of strings `tokens` representing an arithmetic expression in **Reverse Polish Notation (RPN)**.

Evaluate the expression and return the result as an integer.

The valid operators are:

```text
+

-

*

/
```

Each operand may be an integer or another expression.

> Division between two integers should truncate toward zero.

---

## Constraints

```text
1 <= tokens.length <= 10^4

tokens[i] is either:

• An integer

• One of "+", "-", "*", "/"
```

---

# Approach: Stack

## Key Idea

Traverse every token.

### If the token is a number

Push it onto the stack.

### If the token is an operator

1. Pop the second operand.
2. Pop the first operand.
3. Perform the operation.
4. Push the result back.

At the end, the stack contains only one value: the answer.

# Why Use a Stack?

When we encounter:

- A number → Store it.
- An operator → Use the last two numbers.

A **stack** naturally provides access to the most recently added elements.

---

# Solution

```python
class Solution:
    def evalRPN(self, tokens):

        stack = []

        for token in tokens:

            if token not in "-+*/:

                stack.append(int(token))

            else:

                b = stack.pop()
                a = stack.pop()

                if token == "+":
                    stack.append(a + b)

                elif token == "-":
                    stack.append(a - b)

                elif token == "*":
                    stack.append(a * b)

                else:
                    stack.append(int(a / b))

        return stack[0]
```

---

# Complexity Analysis

### Time Complexity

```text
O(n)
```

Each token is processed exactly once.

---

### Space Complexity

```text
O(n)
```

In the worst case, all tokens may be numbers and stored in the stack.

---

## Example 1

### Input

```text
tokens = ["2","1","+","3","*"]
```

### Output

```text
9
```

### Explanation

```text
(2 + 1) × 3

= 3 × 3

= 9
```

---

## Example 2

### Input

```text
tokens = ["4","13","5","/","+"]
```

### Output

```text
6
```

### Explanation

```text
13 / 5 = 2

4 + 2 = 6
```

---
