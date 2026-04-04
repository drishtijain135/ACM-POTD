# POTD Day 14

## Problem
Given the head of a singly linked list, return true if it is a palindrome, otherwise return false.

## Approach
1. Use two pointers (`slow` and `fast`) to find the middle of the linked list  
2. Reverse the second half of the list  
3. Compare the first half and the reversed second half  
4. If all values match, the list is a palindrome  

## Solution
```cpp
class Solution {
public:
    bool isPalindrome(ListNode* head) {
        if (!head || !head->next) return true;

        // Step 1: Find middle
        ListNode* slow = head;
        ListNode* fast = head;

        while (fast && fast->next) {
            slow = slow->next;
            fast = fast->next->next;
        }

        // Step 2: Reverse second half
        ListNode* prev = nullptr;
        while (slow) {
            ListNode* next = slow->next;
            slow->next = prev;
            prev = slow;
            slow = next;
        }

        // Step 3: Compare both halves
        ListNode* left = head;
        ListNode* right = prev;

        while (right) {
            if (left->val != right->val) return false;
            left = left->next;
            right = right->next;
        }
```

## Screenshot
<img width="1919" height="818" alt="image" src="https://github.com/user-attachments/assets/c86475aa-269c-4abe-8946-a2e15f017fb4" />


        return true;
    }
};
