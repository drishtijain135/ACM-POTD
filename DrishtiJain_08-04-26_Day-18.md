# POTD Day 18

## Problem
Given a string `s`, repeatedly remove adjacent duplicate characters until no duplicates remain.  
Return the final string.

## Approach
Use a string as a stack:
- Traverse each character in the string  
- If the current character is the same as the last character of the result, remove it (pop)  
- Otherwise, add it to the result (push)  

This simulates stack behavior and ensures all adjacent duplicates are removed.

## Solution
```cpp
class Solution {
public:
    string removeDuplicates(string s) {
        string st = "";

        for (char c : s) {
            if (!st.empty() && st.back() == c) {
                st.pop_back();
            } else {
                st.push_back(c);
            }
        }

        return st;
    }
};
```

## Screenshot
<img width="1919" height="825" alt="image" src="https://github.com/user-attachments/assets/1ee81675-3a59-463c-a714-4c92613c0557" />
