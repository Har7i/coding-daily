Example 3: Given an integer array nums, find all the numbers x in nums that satisfy the following: x + 1 is not in nums, and x - 1 is not in nums.
If a valid number x appears multiple times, you only need to include it in the answer once.


class solution:
    def example3(self, arr):
        ans = []
        arr_set = set(arr)
        for num in arr_set:
            if num - 1 not in arr_set and num + 1 not in arr_set:
                ans.append(num)
        return ans
        