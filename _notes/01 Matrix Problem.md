---
tags:
  - published
---
## Problem

Given an `m x n` binary [[Matrix]] `mat`, return _the distance of the nearest_ `0` _for each cell_.

The distance between two adjacent cells is `1`.

**Example 1:**

```
Input: mat = [[0,0,0],[0,1,0],[0,0,0]]
Output: [[0,0,0],[0,1,0],[0,0,0]]
```

**Example 2:**

```
Input: mat = [[0,0,0],[0,1,0],[1,1,1]]
Output: [[0,0,0],[0,1,0],[1,2,1]]
```

## Solution

This problem can be solved by performing a [[Breadth First Search (BFS)]] on the matrix. Note that we are not performing a breadth first search on an Adjacency Matrix representation of a graph, but rather the matrix itself. Each zero cell in the matrix is added to a queue which is dequeued and appended 

```Python
class Solution:
    def updateMatrix(self, mat: List[List[int]]) -> List[List[int]]:
        m, n = len(mat), len(mat[0])
        DIR = [0, 1, 0, -1, 0]

        q = deque([])
        for r in range(m):
            for c in range(n):
                if mat[r][c] == 0:
                    q.append((r, c))
                else:
                    mat[r][c] = -1  # Marked as not processed yet!

        while q:
            r, c = q.popleft()
            for i in range(4): # For all adjacent cells
                nr, nc = r + DIR[i], c + DIR[i + 1] # Get cell index
                if nr < 0 or nr == m or nc < 0 or nc == n or mat[nr][nc] != -1: continue
                mat[nr][nc] = mat[r][c] + 1
                q.append((nr, nc))
        return mat
```


![[0de8711a-bdd9-4da3-a094-012abe995508_1627576450.2849615.png]]
