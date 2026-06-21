# 1108. Defanging an IP Address

## Problem

Given a valid IPv4 address `address`, return a defanged version of that IP address.

A defanged IP address replaces every period `.` with `"[.]"`.

**LeetCode Link:** https://leetcode.com/problems/defanging-an-ip-address/

---

## Approach 1: Replace Function

Use Python's built-in `replace()` method.

Replace every:

```text
.
```

with:

```text
[.]
```

---

## Solution (Python)

```python
class Solution:
    def defangIPaddr(self, address):
        return address.replace(".", "[.]")
```

---

## Complexity Analysis

### Time Complexity

```text
O(n)
```

Every character is visited once.

### Space Complexity

```text
O(n)
```

A new string is created.

---

## Approach 2: Build String Manually

```python
class Solution:
    def defangIPaddr(self, address):

        result = ""

        for ch in address:

            if ch == ".":
                result += "[.]"
            else:
                result += ch

        return result
```

---

## Complexity Analysis

### Time Complexity

```text
O(n)
```

### Space Complexity

```text
O(n)
```

---

## Example

Input:

```text
address = "255.100.50.0"
```

Output:

```text
"255[.]100[.]50[.]0"
```

---

## Concepts Used

- String Manipulation
- Traversal
- Replace Function

---

