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
  
import unittest

class TestStringMethods(unittest.TestCase):

  def test_1(self):
      m = []
      expected = []
      self.assertEqual(zeroMatrix(m), expected)

  def test_2(self):
      m = [[1, 0, 1], [1, 1, 1]]
      expected = [[0,0,0], [1, 0,1]]
      self.assertEqual(zeroMatrix(m), expected)

if __name__ == '__main__':
    unittest.main()
```

следующий вариант решения - если нашли 0 то скипаем строчку и столбец так как там всё равно нули будут
```python3
def zeroMatrix(matrix):
  if len(matrix) == 0: return matrix
  
  m = len(matrix)
  n = len(matrix[0])
  
  cols = set()
  rows = set()
  
  i = j = 0
  
  while(i < m):
    while(j < n):
      if matrix[i][j] != 0:
        j += 1
        continue
      
      rows.add(i)
      cols.add(j)
      j += 1
      break
    i += 1
    if j == len(n): j = 0

  for col in cols:
    for i in range(m):
      matrix[i][col] = 0
      
  for row in rows:
    for i in range(n):
      matrix[row][i] = 0

  return matrix
      
      
import unittest

class TestStringMethods(unittest.TestCase):

  def test_1(self):
      m = []
      expected = []
      self.assertEqual(zeroMatrix(m), expected)

  def test_2(self):
      m = [[1, 0, 1], [1, 1, 1]]
      expected = [[0,0,0], [1, 0,1]]
      self.assertEqual(zeroMatrix(m), expected)

if __name__ == '__main__':
    unittest.main()
```
