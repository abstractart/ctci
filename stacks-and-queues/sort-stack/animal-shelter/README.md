```python3
class Node:
  def __init__(self, val, next = None, prev = None):
    self.val = val
    self.next = None
    self.prev = None

class Dog:
  def __init__(self, name):
    self.name = name

class Cat:
  def __init__(self, name):
    self.name = name

class Deque:
  def __init__(self):
    self.head = self.tail = None

  def append(self, val):
    node = Node(val)
    if self.isEmpty():
      self.tail = self.head = node
    else:
      node.prev = self.tail
      self.tail.next = node
      self.tail = node

  def appendLeft(self, val):
    node = Node(val)
    
    if self.isEmpty():
      self.tail = self.head = node
    else:
      node.next = self.head
      self.head = node

  def pop(self):
    if self.isEmpty(): raise

    node = self.tail
    
    self.tail = self.tail.prev
    if self.head == node: self.head = self.head.next

    return node.val
  
  def popLeft(self):
    if self.isEmpty(): raise

    node = self.head

    self.head = self.head.next
    if self.tail == node: self.tail = self.tail.prev
    
    return node.val

  def isEmpty(self):
    return not self.head

class AnimalShelter:
  def __init__(self):
    self.deque = Deque()

  def enqueue(self, animal):
    self.deque.append(animal)

  def dequeueAny(self):
    return self.deque.popLeft()

  def dequeueCat(self):
    return self.dequeueAnimal(Cat)

  def dequeueAnimal(self, t):
    stack = []
    animal = None
    
    while(not self.isEmpty()):
      element = self.deque.popLeft()
      if type(element) is t:
        animal = element
        break
      else:
        stack.append(element)

    while(len(stack) > 0):
      self.deque.appendLeft(stack.pop())
    
    return animal
  def dequeueDog(self):
    return self.dequeueAnimal(Dog)

  def isEmpty(self):
    return self.deque.isEmpty()
```
