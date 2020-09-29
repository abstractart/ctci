# Remove Dups

```python3
class Node:
	def __init__(self, val):
		self.val = val
		self.next = None
		
class Solution:
	def removeDups(self, node, val):
		cache = set()
		
		curr = node
		prev = None
		
		while(curr):
			if curr.val not in cache:
				cache.add(curr.val)
				prev = curr
			  	curr = curr.next
			else:
				prev.next = curr.next
			
			prev = prev.next
			curr = curr.next
```
