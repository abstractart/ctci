
Первое решение через 2 стека
```python3
class Solution:
	def sort(self, stack):
		tmp = []
		
		while(len(stack) > 0):
			e = stack.pop()
			
			if len(tmp) == 0:
				tmp.append(e)
				continue
			
			while(len(tmp) > 0 and tmp[-1] > e):
				stack.append(tmp.pop())
			
			tmp.append(e)
				
		
		while(len(tmp) > 0):
			stack.append(tmp.pop())
```

Второе решение, через один (не подсматривал)
```
class Solution:
	def sort(self, stack):
		tmp = []
		
		while(len(stack) > 0):
			e = stack.pop()
			
			if len(tmp) == 0:
				tmp.append(e)
				continue
			
			while(len(tmp) > 0 and tmp[-1] > e):
				stack.append(tmp.pop())
			
			tmp.append(e)
				
		
		while(len(tmp) > 0):
			stack.append(tmp.pop())
```
