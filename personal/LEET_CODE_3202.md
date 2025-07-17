[3202. Find the Maximum Length of Valid Subsequence II](https://leetcode.com/problems/find-the-maximum-length-of-valid-subsequence-ii/)

Medium

Topics

![premium lock icon](https://leetcode.com/_next/static/images/lock-a6627e2c7fa0ce8bc117c109fb4e567d.svg)Companies

Hint

You are given an integer array `nums` and a **positive** integer `k`.

A subsequence `sub` of `nums` with length `x` is called **valid** if it satisfies:

- `(sub[0] + sub[1]) % k == (sub[1] + sub[2]) % k == ... == (sub[x - 2] + sub[x - 1]) % k.`

Return the length of the **longest** **valid** subsequence of `nums`.

**Example 1:**

**Input:** nums = [1,2,3,4,5], k = 2

**Output:** 5

**Explanation:**

The longest valid subsequence is `[1, 2, 3, 4, 5]`.

**Example 2:**

**Input:** nums = [1,4,2,3,1,4], k = 3

**Output:** 4

**Explanation:**

The longest valid subsequence is `[1, 4, 1, 4]`.

**Constraints:**

- `2 <= nums.length <= 103`
- `1 <= nums[i] <= 107`
- `1 <= k <= 103`
  
  
  solution that i derived.. time limit exceeded issue😂
```python
class Solution:

    def maximumLength(self, nums: list[int], k: int) -> int:

        def get_all_k_length_sub_sequences(nums,k)->List:

            result = set()

            def back_track(index,path):

                if (index == len(nums)):

                    result.add(tuple(path))

                    return

                back_track(index+1,path+[nums[index]])

                back_track(index+1,path)

            back_track(0,[])

            return [list(sequence) for sequence in result]

        all_k_length_sub_sequences = get_all_k_length_sub_sequences(nums,k)

        max_length = 0

        for sub_sequence in all_k_length_sub_sequences:

            if (len(sub_sequence)<2):

                continue

            expected_value = (sub_sequence[0] + sub_sequence[1]) % k

            add_to_count = True

            for index in range(len(sub_sequence)-1):

                if (((sub_sequence[index] + sub_sequence[index+1]) % k) != expected_value):

                    add_to_count = False

                    continue

            if not add_to_count:

                continue

            if (len(sub_sequence) > max_length):

                max_length = len(sub_sequence)

        return max_length
```


ChatGpt's refactored version:
```python


```

Actual solution which i copied..


```python
class Solution:
    def maximumLength(self, nums: list[int], k: int) -> int:
        # Step 1: Create a 2D DP table to track remainder transitions
        dp = [[0] * k for _ in range(k)]  # dp[prev_rem][curr_rem]
        maxLength = 0

        # Step 2: Loop through each number in the array
        for num in nums:
            current_rem = num % k

            # Step 3: Try to extend existing sequences
            for prev_rem in range(k):
                # Step 4: Update the DP table if a transition is possible
                dp[prev_rem][current_rem] = dp[current_rem][prev_rem] + 1

                # Step 5: Track the longest subsequence found so far
                maxLength = max(maxLength, dp[prev_rem][current_rem])

        # Step 6: Return the maximum length found
        return maxLength
```

```


Learnings:
- arrays cannot be added with the numbers
- kind of going to learn the itertools
- lists cannot be assigned to the sets because its not hashable.
- lists can be converted to lists
- backtracking algorithm for sub sequence creation
```python
def get_unique_subsequences(arr):
    result = set()

    def backtrack(index, path):
        if index == len(arr):
            if path:
                result.add(tuple(path))  # Tuples are hashable for set
            return
        # Include current element
        backtrack(index + 1, path + [arr[index]])
        # Exclude current element
        backtrack(index + 1, path)

    backtrack(0, [])
    return [list(seq) for seq in sorted(result)]

```
  
  ![[Backtrack_practice_for_all_possible_sub_sequences.png]]
  
  
  
  