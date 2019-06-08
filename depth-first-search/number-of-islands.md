# Number of Island

---

Given a 2d grid map of`'1'`s \(land\) and`'0'`s \(water\), count the number of islands. An island is surrounded by water and is formed by connecting adjacent lands horizontally or vertically. You may assume all four edges of the grid are all surrounded by water.

**Example 1:**

```
Input:

11110
11010
11000
00000

Output:
 1
```

**Example 2:**

```
Input:

11000
11000
00100
00011

Output: 
3
```

---

```
class Solution(object):
    def numIslands(self, grid):
        """
        :type grid: List[List[str]]
        :rtype: int
        """
        if len(grid) == 0:
            return 0
        M, N = len(grid), len(grid[0])
        count = 0
        for i in range(M):
            for j in range(N):
                if grid[i][j] == '1':
                    count += 1
                    grid[i][j] = '0'
                    self.dfs(grid, M, N, i, j)

        return count

    def dfs(self, grid, M, N, i, j):
        if (i + 1) < M and grid[i + 1][j] == '1':
            grid[i + 1][j] = '0'
            self.dfs(grid, M, N, i + 1, j)
        if (i - 1) >= 0 and grid[i - 1][j] == '1':
            grid[i - 1][j] = '0'
            self.dfs(grid, M, N, i - 1, j)
        if (j + 1) < N and grid[i][j + 1] == '1':
            grid[i][j + 1] = '0'
            self.dfs(grid, M, N, i, j + 1)
        if (j - 1) >= 0 and grid[i][j - 1] == '1':
            grid[i][j - 1] = '0'
            self.dfs(grid, M, N, i, j - 1)
        return
```

---

### Key Learning Points

1. Be mindful of data type
2. self would pass in as the first argument in a private method





