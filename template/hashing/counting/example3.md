Example 3: 1941. Check if All Characters Have Equal Number of Occurrences
Given a string s, determine if all characters have the same frequency.
For example, given s = "abacbc", return true, because all characters appear twice. Given s = "aaabb", return false. "a" appears 3 times, "b" appears 2 times. 3 != 2.

from collections import Counter

class solution:
    def exmaple3(self, s):
        count = Counter(s)
        return len(set(count.values())) == 1