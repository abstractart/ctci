# Zero Matrix

Решение сходу придуманное.

Cложность - квадратичная + линейно растёт память.
```python3
def zeroMatrix(matrix):
  cols = set()
  rows = set()
  
  n = len(m[0])
  m = len(matrix)
  for i in range(m):
    for j in range(n):
      if matrix[i][j] != 0: continue
      
      cols.add(j)
      rows.add(i)
  
  for col in cows:
    for i in range(m):
      matrix[i][col] = 0
      
  for row in rows:
    for i in range(n):
      matrix[row][i] = 0
  
  return matrix
```
