```python3
class Node:
  def __init__(self, val, next = None):
    self.val = val
    self.next = next

class StackMin:
  def __init__(self):
    self.head = None
    self.minimums = dict()
    self.minimums[id(None)] = float('inf')


  # 0(1)
  def push(self, val):
    self.head = Node(val, self.head)
    self.minimums[id(self.head)] = min(
      self.minimums[id(self.head.next)], 
      self.head.val
    )

  
  # O(1)
  def pop(self):
    if self.isEmpty(): raise
    
    val = self.head.val
    del self.minimums[id(self.head)]
    self.head = self.head.next

    return val
	
  def isEmpty(self):
    return not self.head

  def min(self):
    return self.minimums[id(self.head)]


```
