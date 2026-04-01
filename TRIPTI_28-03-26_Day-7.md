# Day 08 - Reverse Linked List

## Problem

https://leetcode.com/problems/reverse-linked-list/

---

## Approach

We reverse the linked list by changing the direction of pointers.

* Use three pointers:

  * `prev` → keeps track of previous node
  * `current` → current node being processed
  * `temp` → stores next node temporarily

### Steps:

* Traverse the list
* Reverse the link (`current->next = prev`)
* Move all pointers one step forward

At the end, `prev` becomes the new head of the reversed list.

---

## Code

```cpp id="k9x2p4"
class Solution {
public:
    ListNode* reverseList(ListNode* head) {
        ListNode* prev = nullptr;
        ListNode* current = head;     
        
        while (current != nullptr) {
            ListNode* temp = current->next;
            current->next = prev;
            prev = current;
            current = temp;
        }
        return prev;                   
    }
};
```

---

## Pattern

Linked List (Pointer Manipulation)

---

## Output Screenshot

<img width="1907" height="859" alt="image" src="https://github.com/user-attachments/assets/fe193da9-5f28-4cd0-9def-0da8208b5bc1" />

