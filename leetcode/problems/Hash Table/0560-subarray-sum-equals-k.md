from collections import defaultdict

class Solution:
    def subarraySum(self, nums: List[int], k: int) -> int:
        prefix_map = defaultdict(int)
        prefix_map[0] = 1
        res, prefix_sum = 0, 0
        for i in range(len(nums)):
            prefix_sum += nums[i]
            res += prefix_map[prefix_sum - k]
            prefix_map[prefix_sum] += 1
        return res