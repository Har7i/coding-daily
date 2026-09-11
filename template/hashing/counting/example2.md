Example 2: 2248. Intersection of Multiple Arrays
Given a 2D array nums that contains n arrays of distinct integers, return a sorted array containing all the numbers that appear in all n arrays.
For example, given nums = [[3,1,2,4,5],[1,2,3,4],[3,4,5,6]], return [3, 4]. 3 and 4 are the only numbers that are in all arrays.

from collections import defaultdict

class solution:
    def example2(self, nums):
        ans = []
        counts = defaultdict(int)
        for arr in nums:
            for i in arr:
                counts[i] += 1
        for key in counts.keys():
            if counts[key] == len(nums):
                ans.append(key)
        ans.sort()
        return ans