# Поворот матрицы

```python3

def rotateMatrix(m):
  result = []
  
  for i in range(len(m)):
    result.append([])
    
  for j in range(len(m):
    for i in reversed(range(len(m))):
      result[j].append(m[i][j])
  
  return result
```

С одной стороны изи алгоритм, а с другой я уже начинаю тупить, выдумывать что-то. Нет бы начать с простого алгоритма.
Это походу из за того что я знал решение инплэйс и мой мозг начал путаться.
