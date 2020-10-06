# Intersection

```python3
class Solution:
  def intersection(self, head1, head2):
    visited = dict()
    
    while(head1):
      visited[id(head1)] = True
      head1 = head1.next
      
    while(head2):
      if id(head2) in visited:
        return True
      head2 = head2.next
      
    return False
```
