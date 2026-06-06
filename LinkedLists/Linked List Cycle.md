# 141. Linked List Cycle

## Problem

**LeetCode Link:** https://leetcode.com/problems/linked-list-cycle/

---

## Approach: Floyd's Cycle Detection Algorithm

Also known as:

```text
Tortoise and Hare Algorithm
```

Use two pointers:

- Slow Pointer → moves 1 step
- Fast Pointer → moves 2 steps

If a cycle exists:

```text
Fast will eventually meet Slow.
```

If no cycle exists:

```text
Fast reaches None.
```

---

## Solution (Python)

```python
class Solution:
    def hasCycle(self, head):

        slow = head
        fast = head
 
        while fast and fast.next:

            slow = slow.next
            fast = fast.next.next

            if slow == fast:
                return True

        return False
```

---

## Complexity Analysis

### Time Complexity

```text
O(n)
```

In the worst case, each node is visited at most a constant number of times.

### Space Complexity

```text
O(1)
```

Only two pointers are used.

---

## Example

### Input

```text
3 -> 2 -> 0 -> -4
     ^         |
     |_________|
```

### Output

```text
True
```

---

## Alternative Approach: Hash Set

Store visited nodes.

```python
class Solution:
    def hasCycle(self, head):

        visited = set()

        while head:

            if head in visited:
                return True

            visited.add(head)

            head = head.next

        return False
```

### Complexity

```text
Time: O(n)
Space: O(n)
```

---

## Why Does Floyd's Algorithm Work?

Suppose:

```text
Slow moves 1 step
Fast moves 2 steps
```

Inside a cycle:

```text
Fast gains 1 node on Slow every iteration.
```

Eventually:

```text
Fast catches Slow.
```

Similar to two runners moving around a circular track.

---

## Concepts Used

- Linked List
- Fast & Slow Pointer
- Floyd's Algorithm
- Cycle Detection

---
