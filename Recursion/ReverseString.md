# Reverse String

## Problem Statement

Given a string `s`, reverse the string and return the reversed result.

---

# Approach 3: Recursion

## Idea

Reverse the remaining string and place the first character at the end.

---

## Solution

```python
def reverseString(s):

    if len(s) <= 1:
        return s

    return reverseString(s[1:]) + s[0]
```

---

## Complexity Analysis

### Time Complexity

```text
O(n²)
```

String concatenation creates new strings repeatedly.

### Space Complexity

```text
O(n)
```

Recursion stack.

---

## Example 1

### Input

```text
s = "hello"
```

### Output

```text
"olleh"
```

---

## Concepts Used

- Two Pointers
- String Manipulation
- Recursion
- Swapping

---

# Note 
- This is not the best of our intrest to solve it recursively , since it's time complexcity is O(n^2).
- For this question we can use either two pointer or use the string slicing.
