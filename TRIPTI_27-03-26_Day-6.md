# Day 06 - Check If N and Its Double Exist

## Problem

https://leetcode.com/problems/check-if-n-and-its-double-exist/

---

## Approach

We check every pair of elements to see if one is double of the other.

* Use two loops
* For every element, compare it with every other element
* If `arr[i] == 2 * arr[j]` and `i != j`, return `true`

---

## Code

```cpp id="x2m8q1"
class Solution {
public:
    bool checkIfExist(vector<int>& arr) {
        int n = arr.size();

        for (int i = 0; i < n; i++) {
            for (int j = 0; j < n; j++) {
                if (i != j && arr[i] == 2 * arr[j]) {
                    return true;
                }
            }
        }

        return false;
    }
};
```

---

## Pattern

Brute Force i.e., Nested Loops

---

## Output Screenshot

<img width="1905" height="719" alt="image" src="https://github.com/user-attachments/assets/85af1f81-d6dc-4f3a-a8a1-8c0647a83ab0" />

