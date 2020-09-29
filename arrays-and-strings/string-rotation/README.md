Сам решил

```python3
def stringRotation(s1, s2):
  if len(s1) != len(s2): return False
  
  i = 0
  j = s2.find(s1[i])
  
  if j < 0: return False
  
  while(i < len(s1)):
    if s1[i] == s2[j]:
      i += 1
      j = (j + 1) % len(s2)
    else:
      return False
      
  return True
```
