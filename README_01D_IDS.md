# 01D IDS

## Python Code

```python
graph = {'A':['B','C'], 'B':['D'], 'C':['D'], 'D':['E'], 'E':[]}

def dls(node, goal, limit, path):
    path.append(node)
    if node == goal: return path
    if limit > 0:
        for n in graph[node]:
            result = dls(n, goal, limit-1, path)
            if result: return result
    path.pop()
    return None

def ids(start, goal, max_depth):
    for depth in range(max_depth+1):
        result = dls(start, goal, depth, [])
        if result: return result
    return None

print('IDS Path:', ids('A', 'E', 4))
```
