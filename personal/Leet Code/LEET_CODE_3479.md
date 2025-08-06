You are given two arrays of integers, `fruits` and `baskets`, each of length `n`, where `fruits[i]` represents the **quantity** of the `ith` type of fruit, and `baskets[j]` represents the **capacity** of the `jth` basket.

From left to right, place the fruits according to these rules:

- Each fruit type must be placed in the **leftmost available basket** with a capacity **greater than or equal** to the quantity of that fruit type.
- Each basket can hold **only one** type of fruit.
- If a fruit type **cannot be placed** in any basket, it remains **unplaced**.

Return the number of fruit types that remain unplaced after all possible allocations are made.

**Example 1:**

**Input:** fruits = [4,2,5], baskets = [3,5,4]

**Output:** 1

**Explanation:**

- `fruits[0] = 4` is placed in `baskets[1] = 5`.
- `fruits[1] = 2` is placed in `baskets[0] = 3`.
- `fruits[2] = 5` cannot be placed in `baskets[2] = 4`.

Since one fruit type remains unplaced, we return 1.

**Example 2:**

**Input:** fruits = [3,6,1], baskets = [6,4,7]

**Output:** 0

**Explanation:**

- `fruits[0] = 3` is placed in `baskets[0] = 6`.
- `fruits[1] = 6` cannot be placed in `baskets[1] = 4` (insufficient capacity) but can be placed in the next available basket, `baskets[2] = 7`.
- `fruits[2] = 1` is placed in `baskets[1] = 4`.

Since all fruits are successfully placed, we return 0.

**Constraints:**

- `n == fruits.length == baskets.length`
- `1 <= n <= 105`
- `1 <= fruits[i], baskets[i] <= 109`
  
  

```python
from typing import List
import math

class Solution:
    def numOfUnplacedFruits(self, fruits: List[int], baskets: List[int]) -> int:
        n = len(baskets)
        blockSize = math.floor(math.sqrt(n))
        blocks = []

        for i in range(0, n, blockSize):
            end = min(i + blockSize, n)
            maxInBlock = -1
            for j in range(i, end):
                if baskets[j] > maxInBlock:
                    maxInBlock = baskets[j]
            blocks.append(maxInBlock)
        
        count = 0
        for fruit in fruits:
            basketFound = False
            for i in range(len(blocks)):
                if (blocks[i] >= fruit):
                    start = i * blockSize
                    end = min(start + blockSize, n)

                    for j in range(start, end):
                        if baskets[j] >= fruit:
                            baskets[j] = -1
                            basketFound = True

                            newMax = -1
                            for k in range(start, end):
                                if (baskets[k] > newMax):
                                    newMax = baskets[k]
                            blocks[i] = newMax
                            break
                if basketFound:
                    break
            if not basketFound:
                count += 1
        return count
```