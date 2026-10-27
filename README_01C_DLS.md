# 01C DLS

## Python Code

```python
graph = {'A':['B','C'], 'B':['D'], 'C':['D'], 'D':['E'], 'E':[]}

def dls(graph, node, goal, limit, path=None):
    if path is None: path = []
    path.append(node)
    if node == goal: return path
    if limit == 0:
        path.pop()
        return None
    for n in graph[node]:
        result = dls(graph, n, goal, limit-1, path)
        if result: return result
    path.pop()
    return None

print('DLS Path:', dls(graph, 'A', 'E', 3))
```
