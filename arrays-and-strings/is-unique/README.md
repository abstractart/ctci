Проверить содержит ли строка повторяющиеся символы
# Python
Линейное время, доп память используется
```python
def isUnique(s):
  counts = dict()

  for c in s:
    if c in counts: return False

    counts[c] = True

  return True 
```

Сортируем символы и пробегаем по ним окном
```python
def isUnique(s):
  chars = sorted(s)

  for i in range(1, len(s)):
    if chars[i] == chars[i - 1]: return False

  return True
```

Подход подсмотренный на SO:
Если строка ASCII то если размер строки больше 256 то в ней точно есть повторы :)
```
