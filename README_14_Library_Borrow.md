# 14 Library Borrow

## Python Code

```python
facts = {'Member(Rahul)', 'ValidID(Rahul)', 'NoFines(Rahul)'}

if 'Member(Rahul)' in facts and 'ValidID(Rahul)' in facts:
    facts.add('LibraryAccess(Rahul)')

if 'LibraryAccess(Rahul)' in facts and 'NoFines(Rahul)' in facts:
    facts.add('CanBorrow(Rahul)')

print('Can borrow book:', 'CanBorrow(Rahul)' in facts)
```
