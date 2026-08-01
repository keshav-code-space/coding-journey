# 84. Largest Rectangle in Histogram

**LeetCode Link:** https://leetcode.com/problems/largest-rectangle-in-histogram/

---

## Problem Statement

Given an array of integers `heights` representing the heights of bars in a histogram, where the width of each bar is `1`, return the **area of the largest rectangle** that can be formed in the histogram.

## Constraints

```text
1 <= heights.length <= 10^5

0 <= heights[i] <= 10^4
```

---

# Approach: Monotonic Increasing Stack

## Step 1

Traverse the histogram from left to right.

---

## Step 2

Push bars while heights are increasing.

Example

```text
2

1

5

6
```

Stack

```text
2

1

5

6
```

---

## Step 3

When a smaller height appears:

```text
2
```

we know:

```text
Bar 6 cannot extend further.

Bar 5 cannot extend further.
```

So we calculate their areas.

---

# Area Formula

When popping a bar:

```text
Height = popped height

Width = current index - previous smaller index - 1
```

Area:

```text
Height × Width
```

---
