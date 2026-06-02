# 1. Two Sum

## Problem
https://leetcode.com/problems/two-sum/

## Approach-1
One brute force approach is to consider every pair of elements and check if their sum equals the target. This can be done using nested loops, where the outer loop iterates from the first element to the second-to-last element, and the inner loop iterates from the next element to the last element.

## Approach-2
A more efficient approach is to use a hash table (unordered_map in C++). We can iterate through the array once, and for each element, check if the target minus the current element exists in the hash table. 

## Solution-1
```python
  class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        n = len(nums)
        for i in range(n - 1):
            for j in range(i + 1, n):
                if nums[i] + nums[j] == target:
                    return [i, j]
        return []  # No solution found
```

## Solution-2

```python
class Solution:
    def twoSum(self, nums, target):
        d = {}
        for i, num in enumerate(nums):
            if target - num in d:
                return [d[target - num], i]
            d[num] = i
```

## Complexity
#### Approach-1

TIME : O(n^2)\
SPACE : O(1)

#### Approach-2

TIME : O(n)\
SPACE : O(1)

