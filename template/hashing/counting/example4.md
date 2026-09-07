Example 4: 560. Subarray Sum Equals K
Given an integer array nums and an integer k, find the number of subarrays whose sum is equal to k.

from collections import defaultdict

class solution:
    def example4(nums, k):
        ans = curr = 0
        counts = defaultdict(int)
        counts[0] = 1
        for num in nums:
            curr += nums
            ans += counts[curr - k]
            counts[curr] += 1
        return ans