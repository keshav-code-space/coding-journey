# 75. Sort Colors

## Problem

Given an array `nums` with `n` objects colored:

```text
0 -> Red
1 -> White
2 -> Blue
```

Sort them in-place so that objects of the same color are adjacent, with the colors in the order:

```text
0, 1, 2
```

You must solve this problem without using the library's sort function.

**LeetCode Link:** https://leetcode.com/problems/sort-colors/

---

## Approach: Dutch National Flag Algorithm

Use three pointers:

```text
low
mid
high
```

Maintain:

```text
[0 ... low-1]     -> 0s
[low ... mid-1]   -> 1s
[mid ... high]    -> Unknown
[high+1 ... end]  -> 2s
```

Process the array until `mid > high`.

---

## Solution (Python)

```python
class Solution:
    def sortColors(self, nums):

        low = 0
        mid = 0
        high = len(nums) - 1

        while mid <= high:

            if nums[mid] == 0:
                nums[low], nums[mid] = nums[mid], nums[low]
                low += 1
                mid += 1

            elif nums[mid] == 1:
                mid += 1

            else:
                nums[mid], nums[high] = nums[high], nums[mid]
                high -= 1
```

---

## Complexity Analysis

### Time Complexity

```text
O(n)
```

Each element is processed at most once.

### Space Complexity

```text
O(1)
```

Sorting is done in-place.

---

## Example

### Input

```text
nums = [2,0,2,1,1,0]
```

### Output

```text
[0,0,1,1,2,2]
```

---

## Alternative Approach: Counting Sort

Count the number of:

```text
0s
1s
2s
```

Then overwrite the array.

```python
class Solution:
    def sortColors(self, nums):

        count0 = nums.count(0)
        count1 = nums.count(1)
        count2 = nums.count(2)

        nums[:count0] = [0] * count0
        nums[count0:count0 + count1] = [1] * count1
        nums[count0 + count1:] = [2] * count2
```

---

