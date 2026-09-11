Example 2: 2260. Minimum Consecutive Cards to Pick Up
Given an integer array cards, find the length of the shortest subarray that contains at least one duplicate. If the array has no duplicates, return -1.

from collections import defaultdict

class solution:
    def example2(self, cards):
        hashmap = defaultdict(int)
        ans = float("inf")
        for i in range(len(cards)):
            if cards[i] in hashmap:
                ans = min(ans, i - hashmap[cards[i]] + 1)
            hashmap[cards[i]] = i
        
        return ans if ans < float("inf") else -1
        