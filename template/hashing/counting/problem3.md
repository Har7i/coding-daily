Maximum Number of Balloons

Solution
Given a string text, you want to use the characters of text to form as many instances of the word "balloon" as possible.

You can use each character in text at most once. Return the maximum number of instances that can be formed.

 

Example 1:



Input: text = "nlaebolko"
Output: 1
Example 2:



Input: text = "loonbalxballpoon"
Output: 2
Example 3:

Input: text = "leetcode"
Output: 0
 

Constraints:

1 <= text.length <= 104
text consists of lower case English letters only.

from collections import Counter

class solution:
    def problem3(self, text):
        count_text = Counter(text)
        count_target = Counter("balloon")
        ans = float("inf")
        for ch in count_text.keys():
            ans = min(ans, count_text[ch] // count_target[ch])
        return ans