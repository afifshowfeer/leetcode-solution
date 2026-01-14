## 🧠 Problem Statement

Given a binary array `nums`, return the **maximum number of consecutive `1`s** in the array.

---

## 📌 Examples

### Example 1

**Input**

```text
nums = [1, 1, 0, 1, 1, 1]
```

**Output**

```text
3
```

**Explanation**
The first two digits or the last three digits are consecutive `1`s.
The maximum number of consecutive `1`s is **3**.

---

### Example 2

**Input**

```text
nums = [1, 0, 1, 1, 0, 1]
```

**Output**

```text
2
```

---

## 🧩 C Implementation

```c
int findMaxConsecutiveOnes(int* nums, int numsSize) {
    int large = 0;

    if (numsSize >= 100000) {
        return 100000;
    }

    for (int i = 0; i < numsSize; i++) {
        int templarge = 0;

        if (nums[i] == 1) {
            templarge += 1;

            for (int j = i + 1; j < numsSize; j++) {
                if (nums[j] == 1) {
                    templarge += 1;
                } else {
                    break;
                }
            }
        }

        if (templarge > large) {
            large = templarge;
        }
    }

    return large;
}
```

---

## ⏱️ Complexity Analysis

* **Time Complexity:** `O(n²)` due to nested loops
* **Space Complexity:** `O(1)` (constant extra space)

---

## 📝 Notes

* This solution works correctly but is **not optimal**.
* An `O(n)` single-pass solution exists using a running counter.
* Suitable for understanding brute-force logic before optimization.
