```python3
class Solution:
	def sort(self, stack):
		sorted_stack = []
		tmp = []
		
		while(len(stack) > 0):
			e = stack.pop()
			
			if len(sorted_stack) == 0:
				sorted_stack.append(e)
				continue
			
			while(len(sorted_stack) > 0 and sorted_stack[-1] > e):
				tmp.append(sorted_stack.pop())
			
			sorted_stack.append(e)
			
			while(len(tmp) > 0):
				sorted_stack.append(tmp.pop())
				
		
		while(len(sorted_stack) > 0):
			stack.append(sorted_stack.pop())
```
