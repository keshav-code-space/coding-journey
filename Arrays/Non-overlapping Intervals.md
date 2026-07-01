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

