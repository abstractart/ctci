pop за константу, push за O(n)
```python3
class MyQueue:
  def __init__(self):
    self.s1 = []
    self.s2 = []

  
  def push(self, val):
    while(len(self.s1) > 0):
      self.s2.append(self.s1.pop())

    self.s1.append(val)

    while(len(self.s2) > 0):
      self.s1.append(self.s2.pop())
    
  def pop(self):
    return self.s1.pop()
```

push за константу, pop за О(n)
```python3
class MyQueue:
  def __init__(self):
    self.s1 = []
    self.s2 = []
  
  def push(self, val):
    self.s1.append(val)
  
  def pop(self):
    while(len(self.s1) > 0):
      self.s2.append(self.s1.pop())

    val = self.s2.pop()

    while(len(self.s2) > 0):
      self.s1.append(self.s2.pop())
    
    return val
```
