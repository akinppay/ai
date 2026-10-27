# 09 HMM Activity

## Python Code

```python
import numpy as np

states = ['Idle','Walking','Running']
obs = ['low','medium','high']
A = np.array([[0.6,0.3,0.1],[0.2,0.6,0.2],[0.1,0.3,0.6]])
B = np.array([[0.7,0.2,0.1],[0.2,0.5,0.3],[0.1,0.2,0.7]])
pi = np.array([0.6,0.3,0.1])
observations = ['low','medium','high']

def viterbi(obs_seq):
    delta = pi * B[:,obs.index(obs_seq[0])]
    for o in obs_seq[1:]:
        delta = np.max(delta[:,None]*A,axis=0)*B[:,obs.index(o)]
    return states[int(np.argmax(delta))]

print('Predicted activity:',viterbi(observations))
```
