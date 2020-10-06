# Three in One
Stack using array (C-style)
```python3
class Stack:
  def __init__(self, capacity):
    self.array = [None] * capacity
    self.top = -1   
  
  def push(self, val):
    if self.isFull(): raise
    
    self.top += 1
    self.array[self.top] = val
	
  def pop(self):
    if self.isEmpty(): raise
    
    val = self.array[self.top]
    self.array[self.top] = None
    self.top -= 1

    return val
	
  def isEmpty(self):
  	return self.top < 0
	
  def isFull(self):
  	return self.top >= len(self.array) - 1
```
