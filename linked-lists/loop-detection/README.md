# Loop detection / Linked List Cycle
https://leetcode.com/problems/linked-list-cycle/
```python3
class Solution(object):
    def hasCycle(self, head):
        if not head: return False
        
        f = head.next
        s = head
        
        while(f and f.next and s):
            if f == s: return True
            f = f.next.next
            s = s.next
            
        return False
```
