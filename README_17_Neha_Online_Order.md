# 17 Neha Online Order

## Python Code

```python
facts = {'ValidPayment(Neha)', 'Account(Neha)', 'DeliveryAddress(Neha)'}

if 'Account(Neha)' in facts and 'ValidPayment(Neha)' in facts:
    facts.add('CanPay(Neha)')

if 'CanPay(Neha)' in facts and 'DeliveryAddress(Neha)' in facts:
    facts.add('CanOrder(Neha)')

print('Can place order:', 'CanOrder(Neha)' in facts)
```
