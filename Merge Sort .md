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

# Merge Function Implementation

```python
def merge(left, right):

    result = []

    i = 0
    j = 0

    while i < len(left) and j < len(right):

        if left[i] <= right[j]:
            result.append(left[i])
            i += 1

        else:
            result.append(right[j])
            j += 1

    while i < len(left):
        result.append(left[i])
        i += 1

    while j < len(right):
        result.append(right[j])
        j += 1

    return result
```

---

# Merge Sort Implementation

```python
def mergeSort(arr):

    if len(arr) <= 1:
        return arr

    mid = len(arr) // 2

    left = mergeSort(arr[:mid])

    right = mergeSort(arr[mid:])

    return merge(left, right)
```

---

# Complete Code

```python
def merge(left, right):

    result = []

    i = 0
    j = 0

    while i < len(left) and j < len(right):

        if left[i] <= right[j]:
            result.append(left[i])
            i += 1

        else:
            result.append(right[j])
            j += 1

    while i < len(left):
        result.append(left[i])
        i += 1

    while j < len(right):
        result.append(right[j])
        j += 1

    return result


def mergeSort(arr):

    if len(arr) <= 1:
        return arr

    mid = len(arr) // 2

    left = mergeSort(arr[:mid])

    right = mergeSort(arr[mid:])

    return merge(left, right)


arr = [8, 3, 5, 4, 7, 6, 1, 2]

print(mergeSort(arr))
```

Output:

```text
[1,2,3,4,5,6,7,8]
```

---

# Time Complexity

## Splitting

The array keeps dividing:

```text
n

n/2

n/4

n/8
```

Number of levels:

```text
log n
```

---

## Merging

At every level:

```text
all n elements are processed
```

Work:

```text
O(n)
```

---

## Total

```text
O(n) × O(log n)

= O(n log n)
```

---

# Space Complexity

```text
O(n)
```

Extra arrays are used during merging.

---
