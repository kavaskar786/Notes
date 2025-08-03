You are given an array of integers `nums` and an integer `target`.

Return _the number of **non-empty** subsequences of_ `nums` _such that the sum of the minimum and maximum element on it is less or equal to_ `target`. Since the answer may be too large, return it **modulo** `109 + 7`.

**Example 1:**
```
```
**Input:** nums = [3,5,6,7], target = 9
**Output:** 4
**Explanation:** There are 4 subsequences that satisfy the condition.
[3] -> Min value + max value <= target (3 + 3 <= 9)
[3,5] -> (3 + 5 <= 9)
[3,5,6] -> (3 + 6 <= 9)
[3,6] -> (3 + 6 <= 9)

**Example 2:**

**Input:** nums = [3,3,6,8], target = 10
**Output:** 6
**Explanation:** There are 6 subsequences that satisfy the condition. (nums can have repeated numbers).
[3] , [3] , [3,3], [3,6] , [3,6] , [3,3,6]

**Example 3:**

**Input:** nums = [2,3,3,4,6,7], target = 12
**Output:** 61
**Explanation:** There are 63 non-empty subsequences, two of them do not satisfy the condition ([6,7], [7]).
Number of valid subsequences (63 - 2 = 61).

Solution that i derived.. memory limit exceeded issue😂
```python
class Solution:

    def numSubseq(self, nums: List[int], target: int) -> int:

        def get_subsequences(lst):

            if not lst:

                return [[]]

            rest = get_subsequences(lst[1:])

            return rest + [[lst[0]] + seq for seq in rest]

        count = 0

        for subseq in get_subsequences(nums):

            if subseq and min(subseq) + max(subseq) <= target:

                count += 1

        return count
```


Actual solution which i copied..

```python
class Solution:
    def numSubseq(self, nums, target):
        mod = 10**9 + 7
        nums.sort()
        n = len(nums)

        power = [1] * n
        for i in range(1, n):
            power[i] = (power[i - 1] * 2) % mod

        left, right = 0, n - 1
        result = 0

        while left <= right:
            if nums[left] + nums[right] <= target:
                result = (result + power[right - left]) % mod
                left += 1
            else:
                right -= 1

        return result
```

