# POTD Day 13

## Problem
Given the heads of two singly linked lists `headA` and `headB`, return the node at which the two lists intersect.  
If the two linked lists have no intersection, return `NULL`.

## Approach
Use two pointers:
- Traverse both lists using pointers `pA` and `pB`  
- When a pointer reaches the end, redirect it to the head of the other list  

This way, both pointers travel equal distances.  
If an intersection exists, they will meet at the intersection node; otherwise, both will become `NULL`.

## Solution
```cpp
class Solution {
public:
    ListNode *getIntersectionNode(ListNode *headA, ListNode *headB) {
        if (!headA || !headB) return nullptr;

        ListNode *pA = headA, *pB = headB;

        while (pA != pB) {
            pA = (pA == nullptr) ? headB : pA->next;
            pB = (pB == nullptr) ? headA : pB->next;
        }

        return pA;
    }
};
```
## Screenshot
<img width="1919" height="815" alt="image" src="https://github.com/user-attachments/assets/86650025-e869-4889-877e-9124a1099e75" />
