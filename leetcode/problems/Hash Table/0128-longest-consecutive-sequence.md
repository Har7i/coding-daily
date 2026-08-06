class Solution:
    def longestConsecutive(self, nums: List[int]) -> int:
        res = 0
        nums = set(nums)
        for num in nums:
            if num - 1 not in nums:
                curr_num = num
                curr_res = 1
                while curr_num + 1 in nums:
                    curr_num += 1
                    curr_res += 1
                res = max(res, curr_res)
        return res