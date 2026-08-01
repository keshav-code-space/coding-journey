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

# Solution

```python
class Solution:
    def largestRectangleArea(self, heights):

        stack = []
        maxArea = 0

        for i, h in enumerate(heights):

            start = i

            while stack and stack[-1][1] > h:

                index, height = stack.pop()

                maxArea = max(maxArea, height * (i - index))

                start = index

            stack.append((start, h))

        while stack:

            index, height = stack.pop()

            maxArea = max(maxArea, height * (len(heights) - index))

        return maxArea
```

---

# Why Store the Start Index?

When a taller bar is removed:

```text
6
```

the next smaller bar:

```text
2
```

can actually start from the same position where `6` started.

So we store:

```python
start = index
```

before pushing the new bar.

This ensures the width is calculated correctly.

---

# Complexity Analysis

### Time Complexity

```text
O(n)
```

Each bar is:

- Pushed once
- Popped once

---

### Space Complexity

```text
O(n)
```

The stack may contain all bars.

---

## Example 1

### Input

```text
heights = [2,1,5,6,2,3]
```

### Output

```text
10
```

### Explanation

The largest rectangle is formed using the bars:

```text
5 and 6
```

Width:

```text
2
```

Area:

```text
5 × 2 = 10
```

---

## Example 2

### Input

```text
heights = [2,4]
```

### Output

```text
4
```

---

# Concepts Used

- Stack
- Monotonic Stack
- Histogram
- Arrays
