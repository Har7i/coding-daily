Example 1: 20. Valid Parentheses
Given a string s containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid. The string is valid if all open brackets are closed by the same type of closing bracket in the correct order, and each closing bracket closes exactly one open bracket.
For example, s = "({})" and s = "(){}[]" are valid, but s = "(]" and s = "({)}" are not valid.

class solution:
    def example1(self, s):
        stack = []
        bracket = {")" : "(", "]" : "[", "}" : "{"}
        for ch in s:
            if ch not in bracket:
                stack.append(ch)
            else:
                if not stack:
                    return False
                temp = stack.pop()
                if temp != bracket(ch):
                    return False
        return not stack