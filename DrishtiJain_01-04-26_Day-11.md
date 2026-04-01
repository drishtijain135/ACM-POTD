# POTD Day 11

## Problem
Given the heads of two sorted linked lists `list1` and `list2`, merge them into a single sorted linked list and return the merged list.

## Approach
Use recursion to merge both lists:
- If one list becomes empty, return the other list  
- Compare the current nodes of both lists  
- Attach the smaller node to the result and recursively merge the remaining nodes  

This ensures the final list remains sorted.

## Solution
```cpp
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode() : val(0), next(nullptr) {}
 *     ListNode(int x) : val(x), next(nullptr) {}
 *     ListNode(int x, ListNode *next) : val(x), next(next) {}
 * };
 */
class Solution {
public:
    ListNode* mergeTwoLists(ListNode* list1, ListNode* list2) {
        // Base case
        if (list1 == nullptr)
            return list2;
        if (list2 == nullptr)
            return list1;

        // Choose smaller value
        if (list1->val <= list2->val) {
            list1->next = mergeTwoLists(list1->next, list2);
            return list1;
        } 
        else {
            list2->next = mergeTwoLists(list1, list2->next);
            return list2;
        }
    }
};
```

## Screenshot
<img width="1919" height="827" alt="image" src="https://github.com/user-attachments/assets/36d7982e-d3aa-4f9e-8fba-44359f9611a9" />
