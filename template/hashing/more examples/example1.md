Example 1: 49. Group Anagrams
Given an array of strings strs, group the anagrams together.
For example, given strs = ["eat","tea","tan","ate","nat","bat"], return [["bat"],["nat","tan"],["ate","eat","tea"]].

from collections import defaultdict

class solution:
    def example1(self, strs):
        hashmap = defaultdict(list)
        for s in strs:
            key = "".join(sorted(s))
            hashmap[key].append(s)
        return list(hashmap.values())