# 88. Merge Sorted Array

**Difficulty:** Easy
**Topics:** Arrays, Two Pointers

---

## 🧠 Problem Statement

You are given two integer arrays `nums1` and `nums2`, both sorted in **non-decreasing order**, and two integers `m` and `n`.

* `nums1` has a length of `m + n`

  * The **first `m` elements** are valid and need to be merged
  * The **last `n` elements** are `0` placeholders
* `nums2` has exactly `n` elements

### 🎯 Goal

Merge `nums2` into `nums1` so that `nums1` becomes a **single sorted array**.

⚠️ **Important constraint:**
Do **not** return anything — modify `nums1` **in-place**.

---

## ✨ Examples

### Example 1

```
Input:
nums1 = [1,2,3,0,0,0], m = 3
nums2 = [2,5,6], n = 3

Output:
[1,2,2,3,5,6]
```

**Explanation:**
We merge `[1,2,3]` and `[2,5,6]` → sorted result stored in `nums1`.

---

### Example 2

```
Input:
nums1 = [1], m = 1
nums2 = [], n = 0

Output:
[1]
```

**Explanation:**
Nothing to merge. `nums1` stays the same.

---

### Example 3

```
Input:
nums1 = [0], m = 0
nums2 = [1], n = 1

Output:
[1]
```

**Explanation:**
`nums1` has no valid elements, so the result is just `nums2`.

---

## 🧩  Solution (Python)

```python
class Solution(object):
    def merge(self, nums1, m, nums2, n):
        if m + n != len(nums1):
            return 0
        if m < 0:
            return 0
        if n > 200:
            return 200
        if m + n > 200:
            return 200

        j = 0
        if n != 0:
            for i in range(m, len(nums1)):
                if nums1[i] < -1000000000:
                    return -1000000000
                if nums2[j] > 1000000000:
                    return 1000000000
                if nums1[i] == 0:
                    nums1[i] = nums2[j]
                    j += 1

        nums1.sort()
```

---

## 🔍 How This Solution Works

1. **Validation checks**

   * Ensures array size correctness
   * Checks constraints on `m`, `n`, and value ranges

2. **Insert elements from `nums2`**

   * Start inserting from index `m` in `nums1`
   * Replace `0` placeholders with values from `nums2`

3. **Sort the final array**

   * Since both arrays were already sorted, sorting guarantees correctness

---

## ⏱️ Time & Space Complexity

* **Time Complexity:** `O((m+n) log(m+n))` due to sorting
* **Space Complexity:** `O(1)` (in-place modification)

---



✨ *Clean logic beats clever logic when you're learning. Optimize later.*
