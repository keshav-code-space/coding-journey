# 160. Intersection of Two Linked Lists

## Problem

**LeetCode Link:** https://leetcode.com/problems/intersection-of-two-linked-lists/

---

## Approach: Two Pointers

### Key Idea

Use two pointers:

```python
pA = headA
pB = headB
```

When a pointer reaches the end:

- `pA` starts from `headB`
- `pB` starts from `headA`

Eventually both pointers travel:

```text
LengthA + LengthB
```

and either:

- Meet at the intersection node
- Reach `None` together

---

## Solution

```python
class Solution:
    def getIntersectionNode(self, headA, headB):

        pA = headA
        pB = headB

        while pA != pB:

            if pA:
                pA = pA.next
            else:
                pA = headB

            if pB:
                pB = pB.next
            else:
                pB = headA

        return pA
```

---

## Complexity Analysis

### Time Complexity

```text
O(m + n)
```

Where:

- m = length of List A
- n = length of List B

---

### Space Complexity

```text
O(1)
```

Only two pointers are used.

---

## Why Does This Work?

Suppose:

```text
LengthA = a + c
LengthB = b + c
```

Where:

```text
c = common part
```

After switching lists:

```text
pA travels a + c + b
pB travels b + c + a
```

Both distances are equal.

Hence they arrive at the intersection simultaneously.

---

## Alternative Approach: Hash Set

Store all nodes of List A.

Then traverse List B.

The first node already present in the set is the intersection.

```python
visited = set()
```

### Complexity

```text
Time: O(m + n)
Space: O(m)
```

---

## Example

### Input

```text
List A: 4 -> 1 \
              8 -> 4 -> 5
List B: 5 -> 6 -> 1 /
```

### Output

```text
Node with value 8
```

---

## Concepts Used

- Linked List
- Two Pointers
- Pointer Switching
- Mathematical Observation

---

## Key Learning

This is one of the most elegant Linked List problems.

Instead of calculating lengths explicitly:

```text
Switch heads when reaching the end.
```

This automatically aligns both pointers.

A useful interview pattern:

```text
Different Length Lists
→ Two Pointer Switching
```

---

## Pattern

- Two Pointers
- Linked List Traversal
- Pointer Switching
- Length Equalization
