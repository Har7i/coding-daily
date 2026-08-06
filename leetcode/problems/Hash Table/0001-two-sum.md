class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        hashtable = {}
        for i in range(len(nums)):
            if target - nums[i] not in hashtable:
                hashtable[nums[i]] = i
            else:
                return [hashtable[target - nums[i]], i]

