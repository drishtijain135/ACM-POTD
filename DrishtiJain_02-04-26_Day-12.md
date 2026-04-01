# POTD Day 12

## Problem
Given the head of a sorted linked list, delete all duplicates such that each element appears only once.  
Return the linked list sorted as well.

## Approach
Traverse the linked list using a pointer:
- Compare current node with next node  
- If values are equal, skip the next node by changing links  
- Otherwise, move forward  

Since the list is sorted, duplicates will always be adjacent.

## Solution
```cpp
class Solution {
public:
    ListNode* deleteDuplicates(ListNode* head) {

        if (head == NULL)
            return NULL;

        ListNode* temp = head;

        while (temp->next != NULL) {
            if (temp->val == temp->next->val) {
                temp->next = temp->next->next;
            } else {
                temp = temp->next;
            }
        }

        return head;
    }
};
```

## Screenshot
<img width="1919" height="821" alt="image" src="https://github.com/user-attachments/assets/47858962-2527-4757-8568-6044a1acceb9" />
