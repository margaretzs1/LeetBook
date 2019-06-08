# Two Sum

---

Given an array of integers, return indices of the two numbers such that they add up to a specific target.

You may assume that each input would have\_**exactly**\_one solution, and you may not use the\_same\_element twice.

**Example:**

```
Given nums = [2, 7, 11, 15], target = 9,

Because nums[0] + nums[1] = 2 + 7 = 9,
return [0, 1].
```

---

```
class Solution(object):
    def twoSum(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: List[int]
        """
        d = dict()

        for i, num in enumerate(nums):
            find = target - num
            if find in d:
                return (d[find], i)
            else:
                d[num] = i
```

---

### Key Learning Points

1. for **index**, **value** in **enumerate**\(Array\)
2. Dictionary: d = **dict\(\)**



