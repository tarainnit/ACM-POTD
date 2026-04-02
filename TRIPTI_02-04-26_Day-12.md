# Day 12 - Remove Duplicates from Sorted List

## Problem

https://leetcode.com/problems/remove-duplicates-from-sorted-list/

---

## Approach

Since the linked list is sorted, duplicate values appear next to each other.

We traverse the list using a pointer (`current`):

* If the current node and the next node have the same value, skip the next node by updating the pointer
* Otherwise, move to the next node

This way, we remove duplicates in-place without using extra space.

---

## Code

```cpp
class Solution {
public:
    ListNode* deleteDuplicates(ListNode* head) {
        ListNode* current = head;

        while (current != nullptr && current->next != nullptr) {
            if (current->val == current->next->val) {
                current->next = current->next->next; // skip duplicate
            } else {
                current = current->next; // move forward
            }
        }

        return head;
    }
};
```

---

## Pattern

Linked List Traversal (In-place modification)

---

## Key Concepts

* Sorted property ensures duplicates are adjacent
* No extra memory needed
* Modify links instead of creating new nodes

---

## Output Screenshot

<img width="1876" height="848" alt="image" src="https://github.com/user-attachments/assets/f0bbbc8d-8997-4e5a-a3e4-9fd8e5f1a028" />

