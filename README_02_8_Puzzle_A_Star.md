# 02 8 Puzzle A Star

## Python Code

```python
from heapq import heappush, heappop

start = (1,2,3,4,0,5,6,7,8)
goal = (1,2,3,4,5,6,7,8,0)

def neighbors(s):
    i = s.index(0)
    r,c = divmod(i,3)
    out = []
    for dr,dc in [(1,0),(-1,0),(0,1),(0,-1)]:
        nr,nc = r+dr,c+dc
        if 0 <= nr < 3 and 0 <= nc < 3:
            j = nr*3+nc
            l = list(s)
            l[i],l[j] = l[j],l[i]
            out.append(tuple(l))
    return out

def h(s):
    return sum(abs(i//3-goal.index(v)//3)+abs(i%3-goal.index(v)%3)
               for i,v in enumerate(s) if v)

def a_star():
    q = [(h(start),0,start)]
    best = {start:0}
    while q:
        f,g,s = heappop(q)
        if s == goal: return g
        if g > best[s]: continue
        for n in neighbors(s):
            ng = g+1
            if ng < best.get(n,float('inf')):
                best[n] = ng
                heappush(q,(ng+h(n),ng,n))
    return None

print('Moves:', a_star())
```
