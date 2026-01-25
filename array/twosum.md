# Two Sum – Optimized Solution (O(n))

## 🧠 Problem Recap

You’re given:

* An integer array `nums`
* An integer `target`

Your task is to **return indices of two numbers** such that:

```
nums[i] + nums[j] == target
```

Constraints guarantee:

* Exactly **one valid solution** exists
* You **cannot reuse the same element twice**

---

## 🚀 Optimal Approach: Hash Map (Dictionary)

Instead of checking every pair (which is **O(n²)**), we can solve this in **O(n)** using a hash map.

### 💡 Core Idea

While traversing the array:

1. For each number `num`, calculate its **complement**:

   ```
   complement = target - num
   ```
2. Check if this complement already exists in a dictionary.

   * If yes → solution found 🎯
   * If no → store the current number with its index

---

## 🧩 Algorithm Steps

1. Create an empty dictionary `prev_dict`
2. Loop through the array using `enumerate`
3. For each element:

   * Check if `target - num` exists in `prev_dict`
   * If found, return both indices
   * Otherwise, store `num` with its index

---

## 🧑‍💻 Python Implementation

```python
class Solution(object):
    def twoSum(self, nums, target):
        prev_dict = {}
        for i, num in enumerate(nums):
            if target - num in prev_dict:
                return [i, prev_dict[target - num]]
            else:
                prev_dict[num] = i
        return -1
```

---

## 🔍 Example Walkthrough

**Input:**

```
nums = [2, 7, 11, 15]
target = 9
```

| Index | Num | Complement | Dictionary | Action              |
| ----- | --- | ---------- | ---------- | ------------------- |
| 0     | 2   | 7          | {}         | Store 2 → 0         |
| 1     | 7   | 2          | {2:0}      | Found! Return [1,0] |

---

## ⏱️ Time & Space Complexity

* **Time Complexity:** `O(n)` – single pass through array
* **Space Complexity:** `O(n)` – dictionary storage

---

## 🤯 Why This Beats O(n²)?

* Brute force checks **every pair** → slow for large inputs
* Hash map gives **constant-time lookup** → lightning fast ⚡

---


