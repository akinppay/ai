# 13 Tomato Disease

## Python Code

```python
facts = {'InGarden(Tomato)', 'YellowLeaves(Tomato)', 'BrownSpots(Tomato)'}

if 'YellowLeaves(Tomato)' in facts:
    facts.add('NutrientDeficiency(Tomato)')

if 'BrownSpots(Tomato)' in facts:
    facts.add('Disease(Tomato)')

print('Disease detected:', 'Disease(Tomato)' in facts)
```
