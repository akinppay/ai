# 05 Tic Tac Toe Minimax

## Python Code

```python
import math

def winner(b):
    lines = [(0,1,2),(3,4,5),(6,7,8),(0,3,6),(1,4,7),(2,5,8),(0,4,8),(2,4,6)]
    for i,j,k in lines:
        if b[i] and b[i] == b[j] == b[k]: return b[i]
    return 'Draw' if all(b) else None

def minimax(b,turn,alpha=-math.inf,beta=math.inf):
    w = winner(b)
    if w == 'O': return 1
    if w == 'X': return -1
    if w == 'Draw': return 0
    scores = []
    for i in range(9):
        if not b[i]:
            b[i] = turn
            next_turn = 'O' if turn == 'X' else 'X'
            scores.append(minimax(b,next_turn,alpha,beta))
            b[i] = ''
            if turn == 'O': alpha = max(alpha,max(scores))
            else: beta = min(beta,min(scores))
            if alpha >= beta: break
    return max(scores) if turn == 'O' else min(scores)

board = ['O','X','X','O','X','','','','']
print(minimax(board,'O'))
```
