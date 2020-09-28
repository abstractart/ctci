# One Away

Моё решение:
```python3
def oneAway(s1, s2):
  if s1 == s2: return True
  if abs(len(s1) - len(s2)) > 1: return False
  
  if len(s2) > len(s1): s1, s2 = s2, s1
  
  i = j = 0
  mismatches = 0
  
  while(i < len(s1) or j < len(s2)):
    if j >= len(s2):
      mismatches += 1
      i += 1
      continue

    if s1[i] == s2[j]:
      i += 1
      j += 1
    else:
      mismatches += 1
      if len(s1) == len(s2): j+= 1
      i += 1
      
  return mismatches <= 1

import unittest

class TestStringMethods(unittest.TestCase):

  def test_1(self):
      self.assertEqual(oneAway("pale", "ple"), True)

  def test_2(self):
      self.assertEqual(oneAway("pales", "pale"), True)

  def test_3(self):
      self.assertEqual(oneAway("pale", "bale"), True)

  def test_4(self):
      self.assertEqual(oneAway("pale", "bake"), False)

if __name__ == '__main__':
    unittest.main()
```
