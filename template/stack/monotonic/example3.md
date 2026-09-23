Example 3: 1438. Longest Continuous Subarray With Absolute Diff Less Than or Equal to Limit
Given an array of integers nums and an integer limit, return the size of the longest subarray such that the absolute difference between any two elements of this subarray is less than or equal to limit.

from collections import deque

class solution:
    def example3(self, nums, limit):
        left = res = 0
        increase = deque()
        decrease = deque()
        for right in range(len(nums)):
            while increase and increase[-1] > nums[right]:
                increase.pop()
            while decrease and decrease[-1] < nums[right]:
                decrease.pop()
            increase.append(nums[right])
            decrease.append(nums[right])
            while decrease[0] - increase[0] > limit:
                if increase[0] == nums[left]:
                    increase.popleft()
                if decrease[0] == nums[left]:
                    decrease.popleft()
                left += 1
            res = max(res, right - left + 1)
        return res