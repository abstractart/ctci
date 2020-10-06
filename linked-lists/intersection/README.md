# Intersection
https://leetcode.com/problems/intersection-of-two-linked-lists/
Собственное решение:
```python3
class Solution:
    def getIntersectionNode(self, head1, head2):
        visited = dict()
    
        while(head1):
            visited[id(head1)] = True
            head1 = head1.next
      
        while(head2):
            if id(head2) in visited:
                return head2
            head2 = head2.next
      
        return None
```

Идеальное с литкода:
```python3
class Solution:
    # @param two ListNodes
    # @return the intersected ListNode
    def getIntersectionNode(self, headA, headB):
        if headA is None or headB is None:
            return None

        pa = headA # 2 pointers
        pb = headB

        while pa is not pb:
            # if either pointer hits the end, switch head and continue the second traversal, 
            # if not hit the end, just move on to next
            pa = headB if pa is None else pa.next
            pb = headA if pb is None else pb.next

        return pa # only 2 ways to get out of the loop, they meet or the both hit the end=None
```
