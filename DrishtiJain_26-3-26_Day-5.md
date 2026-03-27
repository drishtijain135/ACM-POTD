# POTD Day 5

## Problem
Given an array `nums`, move all 0's to the end while maintaining the relative order of the non-zero elements.

## Approach
1. First, find the index of the first zero in the array.  
2. Then traverse the rest of the array, and whenever a non-zero element is found, swap it with the zero and move the zero pointer forward.  
3. This way, all non-zero elements shift to the front and zeroes move to the end.

## Solution
```cpp
class Solution {
public:
    void moveZeroes(vector<int>& nums) {
        int i, j=-1;
        for(i=0 ; i<nums.size(); i++){
            if(nums[i]==0){
                j=i;
                break;
            }
        }

        if(j == -1) return;

        for(i=j+1 ;i<nums.size(); i++){
            if(nums[i]!=0){
                swap(nums[i],nums[j]);
                j++;
            }
        }

    }
};
```

#Screenshot
<img width="1919" height="825" alt="image" src="https://github.com/user-attachments/assets/cd94dc64-c75d-48dd-a00a-aa3450335a9e" />

