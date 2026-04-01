# Day 09 - Linked List Cycle

## Problem

https://leetcode.com/problems/linked-list-cycle/

---

## Approach

We use the **Floyd’s Cycle Detection Algorithm (Two Pointers)**:

* Use two pointers:

  * `slow` → moves one step at a time
  * `fast` → moves two steps at a time

* If there is **no cycle**, `fast` will reach `NULL`
* If there **is a cycle**, `fast` and `slow` will eventually meet

---

## Code

```cpp id="m7x3q2"
class Solution {
public:
    bool hasCycle(ListNode *head) {
        ListNode* slow = head;
        ListNode* fast = head;

        while (fast != nullptr && fast->next != nullptr) {
            slow = slow->next;
            fast = fast->next->next;

            if (slow == fast) {
                return true;
            }
        }

        return false;
    }
};
```

---

## Pattern

Two Pointers (Fast & Slow Pointer Technique)

---

## Output Screenshot

<img width="1899" height="861" alt="image" src="https://github.com/user-attachments/assets/bb950278-f43e-4814-bfe6-1d568a227e25" />

