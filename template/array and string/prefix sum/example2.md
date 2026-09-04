Example 2: 2270. Number of Ways to Split Array

Given an integer array nums, find the number of ways to split the array into two parts so that the first section has a sum greater than or equal to the sum of the second section. The second section should have at least one number.

class solution:
    def example2(nums):
        left_sec, ans = 0, 0
        total = sum(nums)
        for i in range(len(nums) - 1):
            left_sec += nums[i]
            right_sec = total - left_sec
            if left_sec >= right_sec:
                ans += 1
        return ans
