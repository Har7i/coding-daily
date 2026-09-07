Contiguous Array

Solution
Given a binary array nums, return the maximum length of a contiguous subarray with an equal number of 0 and 1.

 

Example 1:

Input: nums = [0,1]
Output: 2
Explanation: [0, 1] is the longest contiguous subarray with an equal number of 0 and 1.
Example 2:

Input: nums = [0,1,0]
Output: 2
Explanation: [0, 1] (or [1, 0]) is a longest contiguous subarray with equal number of 0 and 1.
Example 3:

Input: nums = [0,1,1,1,1,1,0,0,0]
Output: 6
Explanation: [1,1,1,0,0,0] is the longest contiguous subarray with equal number of 0 and 1.
 

Constraints:

1 <= nums.length <= 105
nums[i] is either 0 or 1.

from collections import defaultdict

class solution:
    def problem4(nums):
        ans = curr = 0
        counts = defaultdict(int)
        counts[0] = - 1 
        for i, num in enumerate(nums):
            if num == 1:
                curr += 1
            else:
                curr -= 1
            if curr in counts:
                ans = max(ans, i - counts[curr])
            else:
                counts[curr] = i
        return ans