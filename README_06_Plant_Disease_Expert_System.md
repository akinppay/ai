# 06 Plant Disease Expert System

## Python Code

```python
facts = {'yellow_leaves','spots','wilting'}
rules = [({'yellow_leaves','spots'},'fungal_infection'),
         ({'wilting','fungal_infection'},'plant_disease'),
         ({'yellow_leaves'},'nutrient_deficiency')]

def infer(facts,rules):
    changed = True
    while changed:
        changed = False
        for cond,res in rules:
            if cond <= facts and res not in facts:
                facts.add(res)
                changed = True
    return facts

print(infer(facts,rules))
```
