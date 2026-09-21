Example 3: 844. Backspace String Compare
Given two strings s and t, return true if they are equal when both are typed into empty text editors. '#' means a backspace character.
For example, given s = "ab#c" and t = "ad#c", return true. Because of the backspace, the strings are both equal to "ac".

class solution:
    def example3(self, s, t):
        def build(s):
            stack = []
            for ch in s:
                if ch != "#":
                    stack.append(ch)
                elif stack:
                    stack.pop()
            return "".join(stack)
        return build(s) == build(t)