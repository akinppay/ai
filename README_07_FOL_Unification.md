# 07 FOL Unification

## Python Code

```python
def unify(x,y,sub=None):
    if sub is None: sub = {}
    if x == y: return sub
    if isinstance(x,str) and x.isupper(): return {**sub,x:y}
    if isinstance(y,str) and y.isupper(): return {**sub,y:x}
    if isinstance(x,tuple) and isinstance(y,tuple) and len(x)==len(y):
        for a,b in zip(x,y):
            sub = unify(a,b,sub)
            if sub is None: return None
        return sub
    return None

print(unify(('enrolled','X','ai'),('enrolled','john','ai')))
```
