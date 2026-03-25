# POTD Day 4

## Problem
Given an array nums containing n distinct numbers in the range [0, n], return the only number missing from the array.
## Approach
1. The numbers are in range 0 to n
2. Calculate expected sum using formula:
[
n(n+1)/2
]
3. Calculate actual sum of array
4. Missing number = Expected − Actual
5. This avoids extra space and works in one pass

## Solution
```cpp
class Solution {
public:
    int missingNumber(vector<int>& nums) {
        int n = nums.size();
        int expected = n * (n + 1) / 2;
        int actual = 0;
        for (int x : nums) actual += x;
        return expected - actual;

    }
};
```

## Screenshot
<img width="1916" height="830" alt="image" src="https://github.com/user-attachments/assets/3e3e5e45-3431-46cd-a72a-f4634ae50498" />
