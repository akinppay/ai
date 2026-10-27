# 01B DFS

## Python Code

```python
graph = {'A':['B','C'], 'B':['D'], 'C':['D'], 'D':['E'], 'E':[]}

def dfs(graph, start, goal, visited=None, path=None):
    if visited is None: visited = set()
    if path is None: path = []
    path.append(start)
    visited.add(start)
    if start == goal: return path
    for n in graph[start]:
        if n not in visited:
            result = dfs(graph, n, goal, visited, path)
            if result: return result
    path.pop()
    return None

print('DFS Path:', dfs(graph, 'A', 'E'))
```
