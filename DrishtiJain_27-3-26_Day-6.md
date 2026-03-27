# POTD Day 6

## Problem
Given an array `arr`, check if there exist two indices `i` and `j` such that `i != j` and `arr[i] == 2 * arr[j]`.

## Approach
Use a hash set to store elements while traversing the array.  
For each number:
- Check if its double (`2 * num`) already exists in the set  
- Also check if it is even and its half (`num / 2`) exists  

If any condition is true, return true. Otherwise, insert the number into the set and continue.

## Solution
```cpp
class Solution {
public:
    bool checkIfExist(vector<int>& arr) {
        unordered_set<int> st;

        for (int num : arr) {
            if (st.count(2 * num) || (num % 2 == 0 && st.count(num / 2))) {
                return true;
            }
            st.insert(num);
        }

        return false;
    }
};
```

## Screenshot
<img width="1919" height="831" alt="image" src="https://github.com/user-attachments/assets/5c48f951-3ade-4d5c-bc6e-8a7438cbebc9" />

