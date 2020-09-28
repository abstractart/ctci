```python3
def stringCompression(s):
  if len(s) == 0: return ""
  
  i = 0
  buffer = []
  while(i < len(s)):
    c = s[i]
    count = 0
    
    while(i < len(s) and s[i] == c):
      i += 1
      count += 1
    
    buffer.append(c)
    buffer.append(str(count))
     
  result = "".join(buffer)
  
  if not len(result) < len(s): 
    return s
  
  return result
```
    
