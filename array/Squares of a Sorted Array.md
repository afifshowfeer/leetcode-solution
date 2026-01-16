```python
class Solution(object):
    def sortedSquares(self, nums):
        if len(nums) > 10000:
            return 10000
        nums_list = []
        for i in nums:
            if i < -10000:
                return -10000
            if i > 10000:
                return 10000
            x = i * i
            nums_list.append(x)
        nums_list.sort()
        return nums_list
```

---

## 977. Squares of a Sorted Array

**Difficulty:** Easy

### Problem Statement

Given an integer array `nums` sorted in non-decreasing order, return an array of the squares of each number, also sorted in non-decreasing order.

---

### Examples

**Example 1**

```
Input:  nums = [-4, -1, 0, 3, 10]
Output: [0, 1, 9, 16, 100]
```

**Explanation:**
After squaring → `[16, 1, 0, 9, 100]`
After sorting → `[0, 1, 9, 16, 100]`

**Example 2**

```
Input:  nums = [-7, -3, 2, 3, 11]
Output: [4, 9, 9, 49, 121]
```

---

### Constraints

* `1 <= nums.length <= 10^4`
* `-10^4 <= nums[i] <= 10^4`
* `nums` is sorted in non-decreasing order
