1089. Duplicate Zeros

Difficulty: Easy
Link: https://leetcode.com/problems/duplicate-zeros/


---

Problem Statement

Given a fixed-length integer array arr, duplicate each occurrence of zero, shifting the remaining elements to the right.

Elements beyond the original length are not written

Modify the input array in-place

Do not return anything



---

Examples

Example 1

Input:  [1,0,2,3,0,4,5,0]
Output: [1,0,0,2,3,0,0,4]

Example 2

Input:  [1,2,3]
Output: [1,2,3]


---

Approach

1. Store the original length of the array


2. Traverse the array using index i


3. If arr[i] is 0, insert another 0 at the same index


4. Skip the duplicated zero


5. After traversal, trim the array back to the original length




---

Code (Python)

class Solution(object):
    def duplicateZeros(self, arr):
        length = len(arr)
        i = 0
        
        while i < len(arr):
            if arr[i] == 0:
                arr.insert(i, 0)
                i += 1
            i += 1
        
        del arr[length:]


---

Complexity Analysis

Time Complexity: O(n²)

Space Complexity: O(1)



---

Notes

Uses in-place modification

Simple and readable solution

Suitable for small constraints