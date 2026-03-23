# POTD Day 2

## Problem
Given an array of integers nums and a integer target and return the indices of the two numbers which can add up to give the target.
Each input has exactly one solution and you can not use the same element twice.

## Approach
1. Use a unordered map(hash map) to store the elements and their indices.
2. Traverse the array:
     a. For each element, calculate target - current element i.e. compliment
     b. Check if this compliments exists in map
           if yes--> return indices
           if no --> store that element in map and move to next element
3. This solves the problem in one pass.
4. complexity--> for time complexity  O(NlogN)
                 for space compexity  O(N) as we store elements in map.
   
## Solution
```cpp
map<int,int> mpp;
        int n = nums.size();
        for(int i = 0 ;i<n ; i++){
            int num = nums[i];
            int moreNeeded = target - num;
            if(mpp.find(moreNeeded)!= mpp.end()){
                return {mpp[moreNeeded] ,i};
            }
            mpp[num] = i;
        }
        return {-1,-1};
```

## Screenshot
<img width="1919" height="829" alt="image" src="https://github.com/user-attachments/assets/077d857c-5fe1-44dd-980d-9847fe6421cc" />
