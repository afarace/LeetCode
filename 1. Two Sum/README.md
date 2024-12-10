# Two Sum
## Intuition
The problem requires finding two numbers in a list that add up to a specific target. My first thought is to use a dictionary to store the numbers and their indices as we iterate through the list. This way, we can check if the complement (target - current number) exists in the dictionary, allowing us to find the solution in a single pass.

<!-- Describe your first thoughts on how to solve this problem. -->

## Approach
We iterate through the list of numbers while maintaining a dictionary that maps each number to its index. For each number, we calculate its complement (target - current number) and check if this complement is already in the dictionary. If it is, we have found the two numbers that add up to the target, and we return their indices. If not, we add the current number and its index to the dictionary and continue.

## Complexity
- Time complexity:
The time complexity is $$O(n)$$ because we only iterate through the list once.

- Space complexity:
The space complexity is $$O(n)$$ because we store each number and its index in the dictionary.

## Code

### Python
```python []
class Solution(object):
    def twoSum(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: List[int]
        """
        
        nums_dict = {}

        for i, num in enumerate(nums):
            diff = target - num
            if diff in nums_dict:
                return [nums_dict[diff], i]
            nums_dict[num] = i
```