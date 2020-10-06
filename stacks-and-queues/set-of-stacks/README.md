```python3
class Node:
  def __init__(self, val, next = None, prev = None):
    self.val = val
    self.next = next
    self.prev = prev

class StackArray:
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
	
  def peek(self):
    if self.isEmpty(): raise
    
    return self.array[self.top] 
  
  def isFull(self):
  	return self.top >= len(self.array) - 1


class SetOfStacks:
  def __init__(self, capacity):
    self.set = None
    self.capacity = capacity
  
  def push(self, val):
    if self.isEmpty(): self.append()
    if self.set.val.isFull(): self.append()

    self.set.val.push(val)
  
  def pop(self):  
    while(self.set and self.set.val.isEmpty()):
      self.set = self.set.next
    
    if self.isEmpty(): raise
    
    val =  self.set.val.pop()
    while(self.set and self.set.val.isEmpty()):
      self.set = self.set.next

    return val

  def popAt(self, index):
    curr = self.set
    i = 0
    while(curr and i < index):
      curr = curr.next
      i += 1

    if not curr: raise
    val = curr.val.pop()
    
    if curr.val.isEmpty():
      if curr == self.set:
        self.set = self.set.next
        if self.set: self.set.prev = None
      else:
        curr.prev.next = curr.next 
        if curr.next: curr.next.prev = curr.prev

      return val

  def isEmpty(self):
    return not self.set
  
  def append(self):
    node = Node(StackArray(self.capacity), self.set, None)
    if node.next: node.next.prev = node

    self.set = node


ss = SetOfStacks(1)

ss.push(1)
ss.push(2)
ss.push(3)
```
