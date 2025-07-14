Given `head` which is a reference node to a singly-linked list. The value of each node in the linked list is either `0` or `1`. The linked list holds the binary representation of a number.

Return the _decimal value_ of the number in the linked list.

The **most significant bit** is at the head of the linked list.

**Example 1:**

![](https://assets.leetcode.com/uploads/2019/12/05/graph-1.png)

**Input:** head = [1,0,1]
**Output:** 5
**Explanation:** (101) in base 2 = (5) in base 10

**Example 2:**

**Input:** head = [0]
**Output:** 0

**Constraints:**

- The Linked List is not empty.
- Number of nodes will not exceed `30`.
- Each node's value is either `0` or `1`.
  
  
Solutions:
My solution:
```python
class Solution:

    def getDecimalValue(self, head: Optional[ListNode]) -> int:
        string_values = ""
        while head != None:
            string_values += str(head.val)
            head = head.next
        result = 0
        indexed_length = len(string_values)-1
        get_actual_power_value = lambda indexed_length,index:indexed_length-index
        for index in range(len(string_values)):
            if(string_values[index]== "1"):
                result += 2 ** get_actual_power_value(indexed_length,index)
        return result
```


ChatGpt's solution:
```python
class Solution:
    def getDecimalValue(self, head: Optional[ListNode]) -> int:
        result = 0
        while head:
            result = (result << 1) | head.val  
            head = head.next
        return result
```

Leet code's best solution:
```python
class Solution:
    def getDecimalValue(self, head: Optional[ListNode]) -> int:
        string_values = ""
        while head != None:
            string_values += str(head.val)
            head = head.next          
        return int(string_values,2)
```

Learnings:
- int(string_value, base_value)
	- we can set the base value like (2 for binaries, 10 for decimals)
- lambda function revised

Future learnings:
- shift operators