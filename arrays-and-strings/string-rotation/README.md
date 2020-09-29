Сам решил (Неправильное решение, литкод не одобрил)

```python3
def stringRotation(s1, s2):
  if len(s1) != len(s2): return False
  if len(s1) == 0: return True # Всплыло когда тестил
  
  i = 0
  j = s2.find(s1[i])
  
  if j < 0: return False # Когда писал на листочке об этом кейсе забыл
  
  while(i < len(s1)):
    if s1[i] == s2[j]:
      i += 1
      j = (j + 1) % len(s2)
    else:
      return False
      
  return True
      
      
import unittest

class TestStringMethods(unittest.TestCase):

  def test_1(self):
      s1 = ""
      s2 = ""
      self.assertEqual(stringRotation(s1, s2), True)

  def test_2(self):
      s1 = "wat"
      s2 = "tae"
      self.assertEqual(stringRotation(s1, s2), False)
  def test_3(self):
      s1 = "wat"
      s2 = "taw"
      self.assertEqual(stringRotation(s1, s2), False)

  def test_4(self):
      s1 = "waterbottle"
      s2 = "lewaterbott"
      self.assertEqual(stringRotation(s1, s2), True)

  def test_5(self):
      s1 = "waterbottle"
      s2 = "waterbottle"
      self.assertEqual(stringRotation(s1, s2), True)
if __name__ == '__main__':
    unittest.main()
```


Решение одобренное литкодом:
```python3
class Solution:
    def rotateString(self, s1, s2):
        if len(s1) != len(s2): return False
        if len(s1) == 0: return True

        indexes = self.findChar(s2, s1[0])
        
        for index in indexes:
            j = index
            i = 0
            
            while(i < len(s1) and j < len(s2) and s1[i] == s2[j]):
                j = (j + 1) % len(s2)
                i += 1
                
            if i == len(s1): return True
    
    def findChar(self, s, c):
        indexes = []
        
        for i in range(len(s)):
            if s[i] == c: indexes.append(i)

        return indexes
```
