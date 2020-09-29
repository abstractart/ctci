# Удалить узел из связанного списка имея доступ только к нему
## Моё решение с литкода (линейное время)
```python3
class Solution:
    def deleteNode(self, node):
        curr = node
        prev = None
        
        while(curr.next is not None):
            curr.val = curr.next.val
            prev = curr
            curr = curr.next
            
        prev.next = None
```

## Идеальное Решение: которое придумал / вспомнил уже встретив задачу в книге

```python3
class Solution:
    def deleteNode(self, node):
      node.val = node.next.val
     node.next = node.next.next
```
