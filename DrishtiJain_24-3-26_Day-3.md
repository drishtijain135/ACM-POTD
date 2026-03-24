# POTD Day 3

## Problem
You are given an array prices where prices[i] is the price of a stock on day i.
You want to maximize your profit by choosing a single day to buy and a different day to sell.
Return the maximum profit you can achieve. If no profit is possible, return 0.

## Approach
1. Track the minimum price (mini) seen so far.
2. For each day:
  Calculate profit if sold today → prices[i] - mini
  Update maximum profit
  Update minimum price if current price is smaller
3. This ensures we always buy at the lowest price before selling.

## Solution
```cpp
class Solution {
public:
    int maxProfit(vector<int>& prices) {
        int mini = prices[0];   
        int profit = 0;
        int n = prices.size();
        for(int i=0;i<n;i++){
            int cost = prices[i] - mini;
            profit = max(profit , cost);
            mini = min(mini , prices[i]);
        }
    return profit;
    }
};
```

## Screenshot
<img width="1919" height="822" alt="image" src="https://github.com/user-attachments/assets/1934e495-31e5-4565-beaa-1f3bb04c8b74" />
