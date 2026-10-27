# 04 TSP Hill Climbing SA

## Python Code

```python
import random
import math

cities = [(0,0),(2,4),(5,2),(6,6),(8,3)]

def dist(a,b): return math.dist(cities[a],cities[b])
def cost(p): return sum(dist(p[i],p[(i+1)%len(p)]) for i in range(len(p)))
def neighbor(p):
    i,j = random.sample(range(len(p)),2)
    p[i],p[j] = p[j],p[i]
    return p

def hill_climb():
    cur = list(range(len(cities)))
    random.shuffle(cur)
    for _ in range(1000):
        new = neighbor(cur[:])
        if cost(new) < cost(cur): cur = new
    return cost(cur)

def simulated_annealing():
    cur = list(range(len(cities)))
    random.shuffle(cur)
    T = 100
    for _ in range(1000):
        new = neighbor(cur[:])
        d = cost(new)-cost(cur)
        if d < 0 or random.random() < math.exp(-d/T): cur = new
        T *= 0.99
    return cost(cur)

print('HC Cost:', hill_climb())
print('SA Cost:', simulated_annealing())
```
