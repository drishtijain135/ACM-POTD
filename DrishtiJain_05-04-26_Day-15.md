# POTD Day 15

## Problem
Given a string `s` containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.  
A string is valid if:
- Open brackets are closed by the same type of brackets  
- Open brackets are closed in the correct order  

## Approach
Use a stack:
- Push opening brackets onto the stack  
- For every closing bracket, check the top of the stack  
- If it matches, pop it  
- If it doesn't match or stack is empty, return false  

At the end, if the stack is empty, the string is valid.

## Solution
```cpp
class Solution {
public:
    bool isValid(string s) {
        stack<char> st;

        for (char c : s) {
            if (c == '(' || c == '{' || c == '[') {
                st.push(c);
            } 
            else {
                if (st.empty() ||
                   (c == ')' && st.top() != '(') ||
                   (c == '}' && st.top() != '{') ||
                   (c == ']' && st.top() != '[')) {
                    return false;
                }
                st.pop();
            }
        }

        return st.empty();
    }
};
```

## Screenshot
<img width="1919" height="823" alt="image" src="https://github.com/user-attachments/assets/745cf71e-9ce1-4146-8c56-54ba25068100" />
