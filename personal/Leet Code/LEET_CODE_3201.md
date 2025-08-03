You are given an integer array `nums`.

A subsequence `sub` of `nums` with length `x` is called **valid** if it satisfies:

- `(sub[0] + sub[1]) % 2 == (sub[1] + sub[2]) % 2 == ... == (sub[x - 2] + sub[x - 1]) % 2.`

Return the length of the **longest** **valid** subsequence of `nums`.

A **subsequence** is an array that can be derived from another array by deleting some or no elements without changing the order of the remaining elements.

**Example 1:**

**Input:** nums = [1,2,3,4]

**Output:** 4

**Explanation:**

The longest valid subsequence is `[1, 2, 3, 4]`.

**Example 2:**

**Input:** nums = [1,2,1,1,2,1,2]

**Output:** 6

**Explanation:**

The longest valid subsequence is `[1, 2, 1, 2, 1, 2]`.

**Example 3:**

**Input:** nums = [1,3]

**Output:** 2

**Explanation:**

The longest valid subsequence is `[1, 3]`.

**Constraints:**

- `2 <= nums.length <= 2 * 105`
- `1 <= nums[i] <= 107`

copy pasted solution:
  
``` python
class Solution:

    def maximumLength(self, nums: List[int]) -> int:

        # Constrained 0-1 Knapsack problem.

        # Each element in nums can be chosen or not.

        # Let P(i) be the longest valid sequence length ending with nums[i], with even pairs; Q(i) be the longest valid sequence length ending with nums[i], with odd pairs.

        # P(i) = 1 + max(P(j) for (nums[j] + nums[i]) % 2 == 0)

        # Q(i) = 1 + max(Q(j) for (nums[j] + nums[i]) % 2 == 1)

        # The final answer is max(max(P(i), Q(i))).

        # Base case:

        # P(-1) = 0

        # Q(-1) = 0

        odd_prev_p = 0

        odd_prev_q = 0

        even_prev_p = 0

        even_prev_q = 0

        for num in nums:

            if num % 2 == 1:

                odd_prev_p += 1

                odd_prev_q = 1 + even_prev_q

            else:

                even_prev_p += 1

                even_prev_q = 1 + odd_prev_q

        return max(odd_prev_p, odd_prev_q, even_prev_p, even_prev_q)
```