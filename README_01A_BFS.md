# 01A BFS

## Python Code

```python
from collections import deque

graph = {'A':['B','C'], 'B':['D'], 'C':['D'], 'D':['E'], 'E':[]}

def bfs(graph, start, goal):
    q = deque([(start, [start])])
    visited = {start}
    while q:
        node, path = q.popleft()
        if node == goal:
            return path
        for n in graph[node]:
            if n not in visited:
                visited.add(n)
                q.append((n, path + [n]))
    return None

print('BFS Path:', bfs(graph, 'A', 'E'))
```
