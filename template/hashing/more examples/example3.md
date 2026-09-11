Example 3: 2342. Max Sum of a Pair With Equal Sum of Digits
Given an array of integers nums, find the maximum value of nums[i] + nums[j], where nums[i] and nums[j] have the same digit sum (the sum of their individual digits). Return -1 if there is no pair of numbers with the same digit sum.

from collections import defaultdict

class solution:
    def example3(self, arr):
        def get_digitsum(num):
            digitsum = 0
            while num:
                digitsum += num % 10
                num //= 10
            return digitsum
        
        hashmap = defaultdict(list)
        for num in arr:
            temp = get_digitsum(num)
            hashmap[temp].append(num)
        ans = -1
        for key in hashmap:
            temp = hashmap[key]
            if len(temp) > 1:
                temp.sort(reverse=True)
                ans = max(ans, temp[0] + temp[1])

        return ans