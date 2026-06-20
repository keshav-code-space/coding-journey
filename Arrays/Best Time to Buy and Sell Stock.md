# 121. Best Time to Buy and Sell Stock

## Problem 

You are given an array `prices` where `prices[i]` is the price of a given stock on the `i-th` day.

You want to maximize your profit by choosing a single day to buy one stock and a different day in the future to sell that stock.

Return the maximum profit you can achieve. If no profit can be achieved, return `0`.

**LeetCode Link:** https://leetcode.com/problems/best-time-to-buy-and-sell-stock/


## Approach

Use two pointers:

- `buy` → day to buy the stock for the first iteration we assume it the first element of the array prices
- `profit` → max profit we get

Initially:

```python
buy = prices[0]
profit = 0
```

If `prices[i] - buy > profit`, calculate the profit and update the it.

---

## Solution (Python)

```python
class Solution:
    def maxProfit(self, prices):
        buy = prices[0]
        profit=0
        for i in range(1,len(prices)):
            if prices[i] < buy :
                buy = prices[i]
            elif prices[i]- buy > profit:
                profit = prices[i]-buy
        return profit
```


## Complexity Analysis

### Time Complexity

- O(n)

We traverse the array once.

### Space Complexity

- O(1)

Only a few variables are used.

---

## Concepts Used

- Arrays
- One Pass Traversal
- Optimization

---

