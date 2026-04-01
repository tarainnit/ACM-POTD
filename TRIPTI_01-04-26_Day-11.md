# Day 11 - Merge Two Sorted Lists

## Problem

https://leetcode.com/problems/merge-two-sorted-lists/

---

## Approach

We are given two sorted linked lists and need to merge them into a single sorted linked list.

To solve this, we use a **dummy node** to simplify handling of the result list.

* We maintain a pointer (`temp`) to build the new list.
* Compare the current nodes of both lists:

  * Attach the smaller node to `temp->next`
  * Move that list forward
* Move `temp` forward each time
* After the loop, attach the remaining part of the non-empty list

This ensures the merged list remains sorted.

---

## Code

```cpp
class Solution {
public:
    ListNode* mergeTwoLists(ListNode* list1, ListNode* list2) {
        ListNode* dummy = new ListNode(-1);
        ListNode* temp = dummy;

        while (list1 != nullptr && list2 != nullptr) {
            if (list1->val <= list2->val) {
                temp->next = list1;
                list1 = list1->next;
            } else {
                temp->next = list2;
                list2 = list2->next;
            }
            temp = temp->next;
        }

        if (list1 != nullptr) {
            temp->next = list1;
        } else {
            temp->next = list2;
        }

        return dummy->next;
    }
};
```

---

## Pattern

Two Pointers + Linked List Merging

---

## Key Concepts

* Dummy node simplifies edge cases
* Always attach the smaller node first
* No extra space required (in-place linking)

---

## Output Screenshot

<img width="1886" height="863" alt="image" src="https://github.com/user-attachments/assets/a9e0e29d-9476-4bea-8d67-d0ad0138b5fd" />

