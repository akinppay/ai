# 03 Water Jug

## Python Code

```python
from collections import deque

def bfs(a,b,target):
    q = deque([(0,0)])
    visited = {(0,0)}
    while q:
        x,y = q.popleft()
        if x == target or y == target: return True
        states = [(a,y),(x,b),(0,y),(x,0),
                  (min(x+y,a),max(0,x+y-a)),
                  (max(0,x+y-b),min(x+y,b))]
        for s in states:
            if s not in visited:
                visited.add(s)
                q.append(s)
    return False

print('Possible:', bfs(4,3,2))
```
