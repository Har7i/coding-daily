Example 1: 739. Daily Temperatures
Given an array of integers temperatures that represents the daily temperatures, return an array answer such that answer[i] is the number of days you have to wait after the　ith　day to get a warmer temperature. If there is no future day that is warmer, have answer[i] = 0 instead.

class solution:
    def example1(self, temperatures):
        stack = []
        ans = [0] * len(temperatures)
        for i in range(len(temperatures)):
            while stack and temperatures[stack[-1]] < temperatures[i]:
                j = stack.pop()
                ans[j] = i - j
            stack.append(i)
        return ans