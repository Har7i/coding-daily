Example 4: 2352. Equal Row and Column Pairs
Given an n x n matrix grid, return the number of pairs (R, C) where R is a row and C is a column, and R and C are equal if we consider them as 1D arrays.

from collections import defaultdict

class solution:
    def example4(self, grid):
        ans = 0
        dict = defaultdict(int)
        for row in grid:
            dict[tuple(row)] += 1
        dict1 = defaultdict(int)
        for col in range(len(grid[0])):
            temp_col = []
            for row in range(len(grid)):
                temp_col.append(grid[row][col])
            dict1[tuple(temp_col)] += 1
        for arr in dict:
            ans += dict[arr] * dict1[arr]
        return ans