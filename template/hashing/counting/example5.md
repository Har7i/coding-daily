Given an array of positive integers nums and an integer k. Find the number of subarrays with exactly k odd numbers in them.
For example, given nums = [1, 1, 2, 1, 1], k = 3, the answer is 2. The subarrays with 3 odd numbers in them are [1, 1, 2, 1, 1] and [1, 1, 2, 1, 1].

from collections import defaultdict

class solution:
    def example5(self, nums, k):
        ans = curr = 0
        counts = defaultdict(int)
        counts[0] = 1
        for num in nums:
            curr += num % 2
            ans += counts[curr - k]
            counts[curr] += 1
        return ans
                