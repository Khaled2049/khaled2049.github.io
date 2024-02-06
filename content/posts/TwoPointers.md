---
author: "Khaled Hossain"
title: "Two Pointers"
date: 2023-10-07T18:06:32-06:00
draft: false
description: "Two pointers problems from leetcode"
FAtags: ["python", "tutorial"]
FAcategories: ["python", "tutorial"]
---

```python
def countPairs(self, nums: List[int], target: int) -> int:
    l, r = 0, len(nums) - 1
    pairs = 0
    nums.sort()
    while l < r:
        if (nums[l] + nums[r] < target):
            pairs += r - l
            l += 1
        else:
            r -= 1
    return pairs 
```

1. Initialize two pointers l and r to the beginning and end of the sorted nums list, respectively.
2. Initialize a variable pairs to 0, which will be used to count the pairs that meet the condition.
3. Sort the nums list in ascending order.
4. Use a while loop that continues as long as the left pointer l is less than the right pointer r.
5. Inside the loop, check if the sum of the elements at indices l and r is less than the target.
6. If true, increment pairs by the difference between r and l (since the array is sorted, all elements between l and r will also satisfy the condition), and increment l to move towards larger values.
7. If false, decrement r to move towards smaller values.
Continue the loop until l is no longer less than r.
Return the final count of pairs.

The key idea behind this code is to utilize the fact that the array is sorted. By maintaining two pointers at both ends of the array and adjusting them based on the comparison of the sum with the target, the algorithm efficiently counts pairs that satisfy the specified condition. The sorting step is crucial for this approach to work correctly.


The time complexity of this code is O(n log n), where "n" is the length of the input list nums. The dominant factor contributing to the time complexity is the sorting operation, which has a time complexity of O(n log n).

The while loop has a linear time complexity as it iterates through the sorted array once, making comparisons and updating pointers. However, since the sorting operation has a higher time complexity, it dominates the overall complexity of the algorithm.

Therefore, the overall time complexity is O(n log n) due to the sorting step.