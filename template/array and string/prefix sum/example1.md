Example 1: Given an integer array nums, an array queries where queries[i] = [x, y] and an integer limit, return a boolean array that represents the answer to each query. A query is true if the sum of the subarray from x to y is less than limit, or false otherwise.

For example, given nums = [1, 6, 3, 2, 7, 2], queries = [[0, 3], [2, 5], [2, 4]], and limit = 13, the answer is [true, false, true]. For each query, the subarray sums are [12, 14, 12].

class solution:
    def example1(self, nums, queries, limit):
        prefix = [nums[0]]
        ans = []
        for i in range(1, len(nums)):
            prefix.append(prefix[-1] + nums[i])
        for x, y in queries:
            temp = prefix[y] - prefix[x] + nums[x]
            ans.append(limit > temp)
        return ans
