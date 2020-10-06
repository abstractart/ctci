```python3
class MyQueue:
  def __init__(self):
    self.head = self.tail = None

  def enqueue(self, val):
    node = Node(val)
    if self.isEmpty():
      self.head = self.tail = node
    else:
      self.tail.next = node
      self.tail = self.tail.next

  def dequeue(self):
    if self.isEmpty(): raise

    val = self.head.val

    self.head = self.head.next
    if not self.head: self.tail = None

    return val
  
  def isEmpty(self):
    return not self.head
```
