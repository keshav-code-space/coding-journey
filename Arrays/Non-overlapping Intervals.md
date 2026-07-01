# 435. Non-overlapping Intervals

## Problem Statement

Given an array of intervals where:

```text
intervals[i] = [starti, endi]
```

Return the **minimum number of intervals you need to remove** to make the rest of the intervals **non-overlapping**.

> Two intervals overlap if one interval starts before the previous interval ends.

## Constraints

```text
1 <= intervals.length <= 10^5

intervals[i].length == 2

-5 * 10^4 <= starti < endi <= 5 * 10^4
```

**LeetCode Link:** https://leetcode.com/problems/non-overlapping-intervals/ 

---

# Approach: Greedy

## Key Idea

To maximize the number of intervals we keep, we should always keep the interval that **ends earliest**.

Why?

An interval with a smaller ending time leaves more room for future intervals.

---

# Step 1

Sort the intervals by their ending time.

Example:

```text
Before Sorting

[1,3]

[2,4]

[3,5]

[1,2]
```

Sort by end:

```text
[1,2]

[1,3]

[2,4]

[3,5]
```

---

# Step 2

Keep the first interval.

```text
Previous End = 2
```

---

# Step 3

Traverse the remaining intervals.

If:

```text
current_start >= previous_end
```

No overlap.

Keep it.

Otherwise:

```text
Overlap
```

Remove the current interval.

---

---

# Visualization

Input

```text
[1,2]

[2,3]

[3,4]

[1,3]
```

Sort by ending time

```text
[1,2]

[2,3]

[1,3]

[3,4]
```

Take first:

```text
[1,2]
```

Previous End

```text
2
```

---

Current

```text
[2,3]
```

```text
2 >= 2
```

Keep it.

Previous End

```text
3
```

---

Current

```text
[1,3]
```

```text
1 < 3
```

Overlap.

Remove it.

Count = 1

---

Current

```text
[3,4]
```

```text
3 >= 3
```

Keep it.

Answer

```text
1
```

---

# Solution

```python
class Solution:
    def eraseOverlapIntervals(self, intervals):

        intervals.sort(key=lambda x: x[1])

        count = 0

        prevEnd = intervals[0][1]

        for i in range(1, len(intervals)):

            start = intervals[i][0]
            end = intervals[i][1]

            if start >= prevEnd:

                prevEnd = end

            else:

                count += 1

        return count
```

---

# Dry Run

Input

```text
[[1,2],[2,3],[3,4],[1,3]]
```

Sorted

```text
[1,2]

[2,3]

[1,3]

[3,4]
```

Keep

```text
[1,2]
```

Previous End

```text
2
```

Next

```text
[2,3]
```

Keep

Previous End

```text
3
```

Next

```text
[1,3]
```

Overlap

Remove

```text
count = 1
```

Next

```text
[3,4]
```

Keep

Final Answer

```text
1
```

---

# Why Sort by Ending Time?

Consider:

```text
[1,100]

[2,3]

[3,4]
```

If we keep:

```text
[1,100]
```

We lose both remaining intervals.

Instead, keep:

```text
[2,3]

[3,4]
```

This keeps more intervals and minimizes removals.

Hence, we always choose the interval with the **earliest ending time**.

---

# Complexity Analysis

### Time Complexity

Sorting:

```text
O(n log n)
```

Traversal:

```text
O(n)
```

Overall:

```text
O(n log n)
```

---

### Space Complexity

```text
O(1)
```

(Excluding the sorting algorithm's internal space.)

---

## Example 1

### Input

```text
intervals = [[1,2],[2,3],[3,4],[1,3]]
```

### Output

```text
1
```

### Explanation

Remove:

```text
[1,3]
```

Remaining intervals:

```text
[1,2]

[2,3]

[3,4]
```

No intervals overlap.

---

## Example 2

### Input

```text
intervals = [[1,2],[1,2],[1,2]]
```

### Output

```text
2
```

### Explanation

Only one interval can remain.

---
