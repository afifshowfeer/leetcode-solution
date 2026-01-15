## 🧮 Find Numbers with Even Number of Digits

**Difficulty:** Easy
**Topics:** Arrays, Math

---

### 📌 Problem Statement

Given an array `nums` of integers, return how many of them contain an **even number of digits**.

---

### 🧠 Explanation

For each number in the array:

* Count the number of digits
* If the digit count is even, increment a counter
* Return the final count

---

### ✅ Example 1

**Input**

```
nums = [12, 345, 2, 6, 7896]
```

**Output**

```
2
```

**Explanation**

* `12` → 2 digits ✅
* `345` → 3 digits ❌
* `2` → 1 digit ❌
* `6` → 1 digit ❌
* `7896` → 4 digits ✅

Numbers with even digits: **12, 7896**

---

### ✅ Example 2

**Input**

```
nums = [555, 901, 482, 1771]
```

**Output**

```
1
```

**Explanation**
Only `1771` contains an even number of digits.

---

### 💻 C Implementation

```c
int findNumbers(int* nums, int numsSize) {
    int count = 0;

    for (int i = 0; i < numsSize; i++) {
        int tempcount = 0;
        int num = nums[i];

        while (num != 0) {
            num = num / 10;
            tempcount++;
        }

        if (tempcount % 2 == 0) {
            count++;
        }
    }

    return count;
}
```

---

### ⚠️ Notes

* No need to manually check constraints like array size or maximum value
* LeetCode already guarantees valid inputs
* Focus on solving the core logic cleanly
