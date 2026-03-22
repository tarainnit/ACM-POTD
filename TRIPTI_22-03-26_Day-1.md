# Day 01 - Remove Duplicates from Sorted Array

## Problem

https://leetcode.com/problems/remove-duplicates-from-sorted-array/

---

## Approach

Since the array is sorted, duplicate elements are adjacent.

I used the **two-pointer technique**:
* One pointer (`i`) keeps track of the position of the last unique element.
* Another pointer (`j`) traverses the array.

Whenever a new element (different from the last unique element) is found:
* Move the `i` pointer forward
* Place the new element at position `i`

---

## Code

```python
class Solution:
    def removeDuplicates(self, nums):
        if len(nums) == 0:
            return 0

        i = 0

        for j in range(1, len(nums)):
            if nums[j] != nums[i]:
                i += 1
                nums[i] = nums[j]

        return i + 1
```

---

## Output Screenshot

<img width="941" height="619" alt="image" src="https://github.com/user-attachments/assets/0112677d-9987-4e31-9b36-0d98b43aab1b" />

