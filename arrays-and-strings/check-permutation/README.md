Даны две строки, убедиться что первая является перестановкой второй

# Решение 1
Сортируем оба массива, если они поэлементно равны значит s1 перестановка s2
```python
def checkPermutation(s1, s2):
  return sorted(s1) == sorted(s2)
```
# Решение 2
Построить хэшмапы счётчики и убедиться что они идентичны
```python
from collections import Counter

def checkPermutation(s1, s2):
  return Counter(s1) == Counter(s2)
```

# Решение 3
Как 2 только более развёрнутое
```python
def checkPermutation(s1, s2):
  counts = dict()
  
  for c in s1:
    if c not in counts: counts[c] = 0
    counts[c] += 1
    
   
  for c in s2:
    if c not in counts: return False
    
    counts[c] -= 1
    
    if counts[c] < 0: return False

  for c in counts.keys():
    if counts[c] > 0: return False
    
  return True
```

# Решение 4
Похоже на 3 только используется массив 256 элементов (ASCII) вместо counts
