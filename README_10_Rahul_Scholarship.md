# 10 Rahul Scholarship

## Python Code

```python
facts = {'GoodAttendance(Rahul)', 'GoodPerformance(Rahul)', 'Student(Rahul)'}

if 'Student(Rahul)' in facts and 'GoodAttendance(Rahul)' in facts:
    facts.add('ExamEligible(Rahul)')

if 'ExamEligible(Rahul)' in facts and 'GoodPerformance(Rahul)' in facts:
    facts.add('ScholarshipEligible(Rahul)')

print('Scholarship Eligible:', 'ScholarshipEligible(Rahul)' in facts)
```
