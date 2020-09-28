# One Away

```python3
def oneAway(s1, s2):
  if s1 == s2: return True
  if abs(len(s1) - len(s2)) > 1: return False
  
  if len(s1) > len(s2): s1, s2 = s2, s1
  
  i = j = 0
  mismatches = 0
  
  while(i < len(s1) or j < len(s2)):
    if j >= len(s2) and i < len(s1): mismatches += 1
    
    if s[i] == s[j]:
      i += 1
      j += 1
    else:
      mismatches += 1
      if len(s1) == len(s2): j+= 1
      i += 1
      
  return mismatches <= 1
```
