Собственное решение:
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
Решение через дополнительный стэк
```python3
class Node:
  def __init__(self, val, next = None):
    self.val = val
    self.next = next

class StackMin:
  def __init__(self):
    self.head = None
    self.minimums = list()


  # 0(1)
  def push(self, val):
    self.head = Node(val, self.head)
    self.minimums.append(min(self.min() ,self.head.val))
    	

  
  # O(1)
  def pop(self):
    if self.isEmpty(): raise
    
    val = self.head.val
    self.minimums.pop()
    self.head = self.head.next

    return val
	
  def isEmpty(self):
    return not self.head

  def min(self):
    if len(minimums) == 0: return float('inf')
    return self.minimums[-1]
```
В чём идея - храним для каждого узла стека его минимум,
- при удалении узла удаляем и минимум связанный с ним
- При добавлении элемента вычисляем новый минимум и сохраняем его


**Замечание** - в задаче было указано - все операции за о(1). пуш и поп могут работать за такое время если мы будем хранить минимумы в связном списке у которого удаление из хвоста/головы и добавление константное в голову / хвост константное
