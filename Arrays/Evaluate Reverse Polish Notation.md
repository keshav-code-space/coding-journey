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

---
