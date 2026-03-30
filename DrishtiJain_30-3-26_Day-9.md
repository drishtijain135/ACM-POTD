# POTD Day 9

## Problem
Given the head of a linked list, determine if the linked list has a cycle in it.  
A cycle exists if some node in the list can be reached again by continuously following the next pointer.

## Approach
Use Floyd’s Cycle Detection Algorithm (Tortoise and Hare method).  
Take two pointers:
- `slow` moves one step at a time  
- `fast` moves two steps at a time  

If a cycle exists, both pointers will eventually meet.  
If the fast pointer reaches the end, then there is no cycle.

## Solution
```cpp
class Solution {
public:
    bool hasCycle(ListNode *head) {
        if (!head) return false;

        ListNode *slow = head, *fast = head;

        while (fast && fast->next) {
            slow = slow->next;
            fast = fast->next->next;

            if (slow == fast) return true;
        }

        return false;
    }
};
```
## Screenshot
<img width="1919" height="824" alt="image" src="https://github.com/user-attachments/assets/ac201815-efd1-40a1-b1f8-f98fae33635b" />
