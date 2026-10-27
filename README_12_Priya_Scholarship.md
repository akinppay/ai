# 12 Priya Scholarship

## Python Code

```python
facts = {'Student(Priya)', 'GoodAttendance(Priya)', 'GoodMarks(Priya)'}

if 'Student(Priya)' in facts and 'GoodAttendance(Priya)' in facts:
    facts.add('ExamEligible(Priya)')

if 'ExamEligible(Priya)' in facts and 'GoodMarks(Priya)' in facts:
    facts.add('Scholarship(Priya)')

print('Scholarship eligible:', 'Scholarship(Priya)' in facts)
```
