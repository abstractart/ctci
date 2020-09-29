# Return Kth from last
Решил сам, без особых проблем, складываем значения в массив и достаём последнее
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
