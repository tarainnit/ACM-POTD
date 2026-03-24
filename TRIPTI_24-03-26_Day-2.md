# Day 02 - Best Time to Buy and Sell Stock

## Problem

https://leetcode.com/problems/best-time-to-buy-and-sell-stock/

---

## Approach

We need to maximize profit by buying at the lowest price and selling at the highest price *after* it.

Instead of checking all pairs, we use a **greedy approach**:

* Keep track of the minimum price seen so far
* At each step, calculate the profit if sold on that day
* Update the maximum profit accordingly

This ensures we always buy at the best possible price before selling.

---

## Code

```python
class Solution:
    def maxProfit(self, prices):
        min_price = float('inf')
        max_profit = 0

        for price in prices:
            min_price = min(min_price, price)
            max_profit = max(max_profit, price - min_price)

        return max_profit
```

---

## Pattern

Greedy (Tracking Minimum)

---

## Output Screenshot

<img width="1915" height="874" alt="image" src="https://github.com/user-attachments/assets/61a945d6-bba5-4ba9-a190-44910e05e450" />


(Add your screenshot here)
