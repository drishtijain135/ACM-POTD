# POTD Day 10

## Problem
Given the head of a singly linked list, return the middle node of the linked list.  
If there are two middle nodes, return the second middle node.

## Approach
Use the two-pointer technique:
- `slow` pointer moves one step at a time  
- `fast` pointer moves two steps at a time  

When `fast` reaches the end, `slow` will be at the middle of the linked list.

## Solution
```cpp
class Solution {
public:
    ListNode* middleNode(ListNode* head) {
        ListNode* slow = head, *fast = head;

        while (fast && fast->next) {
            slow = slow->next;
            fast = fast->next->next;
        }

        return slow;
    }
};
```

##Screenshot
<img width="1919" height="825" alt="image" src="https://github.com/user-attachments/assets/3c3e80df-64e6-4687-80b2-5375b4dfec04" />
