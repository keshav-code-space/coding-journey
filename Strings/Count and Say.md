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
