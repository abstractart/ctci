# Дана строка, нужно проверить являтся ли эта строка перестановкой строки палиндрома
Или если по нормальному: проверить можно ли из строки построить палиндром :)

# Решение
1. Постром словарь, ключ - символ, значение - количество вхождений. Учитываем только символы - буквы (спасибо функции isalpha()). Совсем забыл, могут встречатья символы в верхнем и нижнем регистрах. Нужно при вставке в хэшмап приводить к нижнему.

2. Проверим словарь:
- все значения должны быть четными если количество символов чётное. 
- Если длина строки нечётная то должен быть один символ который встречается нечётное количество раз.

Для упрощения: пусть кроме букв встречается только пробел

```python3
def palindromePermutation(s):
  
  len_without_spaces = 0
  counts = dict()
  
  for c in s:
    if c == " ": continue
    if c.lower() not in counts: counts[c.lower()] = 0
    counts[c.lower()] += 1
    len_without_spaces += 1
    
  
  odd_count = 0
  for k in counts.keys():
    if counts[k] % 2 != 0: odd_count += 1
    
  if odd_count == 1 and len_without_spaces % 2 == 1: return True
  if odd_count == 0 and len_without_spaces % 2 == 0: return True
  
  return False
```
    
После того как написал решение:
1. Можно было бы перед циклом всю строку привести к нижнему регистру
2. Можно убрать пробелы совсем

```PYTHON3
def palindromePermutation(s):
  s = s.lower().replace(" ", "")
  counts = dict()
 
  for c in s:
    counts[c] = counts.get(c, 0) + 1
    
  odd = 0
  for c in counts.keys():
    if counts[c] % 2 != 0: odd += 1
    
  if odd == 1 and len(s) % 2 == 1: return True
  if odd == 0 and len(s) % 2 == 0: return True
  
  return False
```
