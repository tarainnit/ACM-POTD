# Day 05 - Move Zeroes

## Problem

https://leetcode.com/problems/move-zeroes/

---

## Approach

We need to move all `0`s to the end while maintaining the relative order of non-zero elements.

This can be solved using the **two-pointer technique**:

* One pointer (`i`) tracks the position to place the next non-zero element
* Another pointer (`j`) traverses the array

Whenever a non-zero element is found:

* Swap it with the element at index `i`
* Increment `i`

This ensures:

* All non-zero elements are shifted forward
* All zeroes automatically move to the end

---

## Code

```python id="s8f2l1"
class Solution:
    def moveZeroes(self, nums):
        i = 0

        for j in range(len(nums)):
            if nums[j] != 0:
                nums[i], nums[j] = nums[j], nums[i]
                i += 1
```

---

## Output Screenshot

<img width="1898" height="844" alt="image" src="https://github.com/user-attachments/assets/f9c1789d-f54e-437a-80f9-24df44434978" />

