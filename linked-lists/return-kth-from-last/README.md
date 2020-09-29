# Return Kth from last
## Решил сам, без особых проблем, складываем значения в массив и достаём последнее
```python3
class Node:
  def __init__(self, val):
    self.val = val
    self.next = None


class Solution:
  def kFromLast(self, node, k):
    if not node: return
    if k <= 0: return

    stack = []
    curr = node
    while(curr):
      stack.append(curr.val)
      curr = curr.next
      
    if k > len(stack): raise
   
    return stack[len(stack) - k]
```

## Решение без доп памяти, через 2 указателя:
Идея: быстрый указатель продвигаем на к элементов вперед.
Медленный указатель оставляем в голове

циклом проходим до конца списка через быстрый указатель

быстрый указатель сделает n - k шагов и станет None

медленный указатель сделает n - k шагов и станет искомым элементом.

```python3
class Node:
  def __init__(self, val):
    self.val = val
    self.next = None

class Solution:
  def kFromLast(self, node, k):
    if not node: return
    
    fast = slow = node
    
    for i in range(k):
      if not fast: return None
      fast = fast.next
      
    
    while(fast):
      fast = fast.next
      slow = slow.next
      
    return slow
```
