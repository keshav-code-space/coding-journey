# Merge Sort

## What is Merge Sort?

Merge Sort is a sorting algorithm that follows the:

```text
Divide and Conquer
```

technique.

Instead of sorting the entire array at once, Merge Sort:

```text
1. Divides the array into smaller parts.
2. Sorts each part recursively.
3. Merges the sorted parts together.
```

---

## Why is it Called Divide and Conquer?

### Divide

Break the array into two halves.

Example:

```text
[8, 3, 5, 4]
```

↓

```text
[8, 3]    [5, 4]
```

↓

```text
[8] [3] [5] [4]
```

---

### Conquer

Sort the smaller parts.

```text
[8]
[3]
[5]
[4]
```

Single-element arrays are already sorted.

---

### Merge

Merge the sorted arrays.

```text
[8] [3]
```

↓

```text
[3, 8]
```

and

```text
[5] [4]
```

↓

```text
[4, 5]
```

Finally:

```text
[3, 8] + [4, 5]
```

↓

```text
[3, 4, 5, 8]
```

---
