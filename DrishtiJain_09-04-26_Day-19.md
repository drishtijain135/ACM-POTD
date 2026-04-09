# POTD Day 19

## Problem
Given two strings `s` and `t`, return true if they are equal when both are typed into empty text editors.  
`#` means a backspace character.

## Approach
Use two pointers starting from the end of both strings:
- Traverse backwards and skip characters affected by `#`  
- Use a helper function to find the next valid character  
- Compare characters of both strings  
- If all match, return true  

This avoids building new strings and works efficiently.

## Solution
```cpp
class Solution {
private:
    int getNextValidChar(string& s, int index) {
        int backspace = 0;

        while (index >= 0) {
            if (s[index] == '#') {
                backspace++;
            } 
            else if (backspace > 0) {
                backspace--;
            } 
            else {
                break;
            }
            index--;
        }

        return index;
    }

public:
    bool backspaceCompare(string s, string t) {
        int i = s.length() - 1;
        int j = t.length() - 1;

        while (i >= 0 || j >= 0) {
            i = getNextValidChar(s, i);
            j = getNextValidChar(t, j);

            if (i >= 0 && j >= 0 && s[i] != t[j]) {
                return false;
            }

            if ((i >= 0) != (j >= 0)) {
                return false;
            }

            i--;
            j--;
        }

        return true;
    }
};
```

## Screenshot
<img width="1919" height="825" alt="image" src="https://github.com/user-attachments/assets/a89188bf-9d39-41a3-9e13-f80dc2896f56" />
