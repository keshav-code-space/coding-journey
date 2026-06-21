# 232. Implement Queue using Stacks

## Problem

Implement a First-In-First-Out (FIFO) queue using only two stacks.

Implement the following operations:

```python
push(x)
pop()
peek()
empty()
```

**LeetCode Link:** https://leetcode.com/problems/implement-queue-using-stacks/

---

## Queue vs Stack

### Queue (FIFO)

```text
Front → 1 → 2 → 3 → Rear
```

First inserted:

```text
1
```

First removed:

```text
1
```

---

### Stack (LIFO)

```text
Top
 ↓
3
2
1
```

Last inserted:

```text
3
```

First removed:

```text
3
```

---

## Approach: Two Stacks

Use:

```python
inputStack
outputStack
```

### Push

Insert into:

```python
inputStack
```

### Pop / Peek

If `outputStack` is empty:

Move all elements from:

```python
inputStack → outputStack
```

This reverses the order.

Then:

```python
pop()  -> outputStack.pop()
peek() -> outputStack[-1]
```

---

## Solution

```python
class MyQueue:

    def __init__(self):
        self.inputStack = []
        self.outputStack = []

    def push(self, x: int) -> None:
        self.inputStack.append(x)

    def pop(self) -> int:

        if not self.outputStack:

            while self.inputStack:
                self.outputStack.append(
                    self.inputStack.pop()
                )

        return self.outputStack.pop()

    def peek(self) -> int:

        if not self.outputStack:

            while self.inputStack:
                self.outputStack.append(
                    self.inputStack.pop()
                )

        return self.outputStack[-1]

    def empty(self) -> bool:

        return (
            not self.inputStack
            and not self.outputStack
        )
```

---

## Complexity Analysis

### Push

```text
O(1)
```

---

### Pop

```text
Amortized O(1)
```

Each element is moved at most once.

---

### Peek

```text
Amortized O(1)
```

---

### Empty

```text
O(1)
```

---

### Space Complexity

```text
O(n)
```

For storing queue elements.

---

## Example

### Input

```text
push(1)
push(2)
peek()
pop()
empty()
```

### Output

```text
1
1
False
```

---

## Concepts Used

- Stack
- Queue
- Amortized Analysis
- Data Structure Design

---
