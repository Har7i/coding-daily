class Solution:
    def decodeString(self, s: str) -> str:
        stack = []
        cur_num, cur_str = 0, ""
        for ch in s:
            if ch.isdigit():
                cur_num = cur_num * 10 + int(ch)
            elif ch == "[":
                stack.append((cur_num, cur_str))
                cur_num, cur_str = 0, ""
            elif ch == "]":
                num, pre_str = stack.pop()
                cur_str = pre_str + cur_str * num
            else:
                cur_str += ch
        return cur_str