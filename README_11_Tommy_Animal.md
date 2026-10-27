# 11 Tommy Animal

## Python Code

```python
facts = {'FourLegs(Tommy)', 'Pet(Tommy)', 'Dog(Tommy)'}

if 'Dog(Tommy)' in facts:
    facts.add('Mammal(Tommy)')

if 'Mammal(Tommy)' in facts:
    facts.add('Animal(Tommy)')

print('Is Tommy an animal:', 'Animal(Tommy)' in facts)
```
