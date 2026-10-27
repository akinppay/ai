# 16 Amit Promotion Repeat

## Python Code

```python
facts = {'FiveYearsService(Amit)', 'GoodPerformance(Amit)', 'Employee(Amit)'}

if 'FiveYearsService(Amit)' in facts:
    facts.add('Experienced(Amit)')

if 'Experienced(Amit)' in facts and 'GoodPerformance(Amit)' in facts:
    facts.add('PromotionEligible(Amit)')

print('Promotion eligible:', 'PromotionEligible(Amit)' in facts)
```
