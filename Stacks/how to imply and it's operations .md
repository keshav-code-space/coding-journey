# Stack Data Structure

## What is a Stack?

A Stack is a linear data structure that follows:

```text
LIFO (Last In First Out)
```

The last element inserted is the first element removed.

Example:

```text
Push 10
Push 20
Push 30

Stack:

Top
 ↓
30
20
10
```

Removing an element:

```text
Pop()

Top
 ↓
20
10
```

---

## Real-Life Examples

### Browser History

```text
Visited:
Google
YouTube
GitHub

Back Button:
GitHub → YouTube → Google
```

### Undo Operation

```text
Type A
Type B
Type C

Undo:
C → B → A
```

---

# Stack Implementation Using Class

```python
