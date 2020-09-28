# URLIFY

```
"Mr John Smith   " => "Mr%20John%20Smith"
```

```python3
def urlify(s, n):
  j = len(s) - 1
  for i in reversed(range(n)):
    if s[i] == " ":
      s[j] = "0"
      s[j - 1] = "2"
      s[j - 2] = "%"
      j -= 3
    else:
      s[j] = s[i]
      j -= 1
    
```
