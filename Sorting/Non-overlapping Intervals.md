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

# Concepts Used

- Greedy Algorithm
- Sorting
- Intervals
- Array
