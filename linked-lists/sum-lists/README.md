Сам с нуля написал, вроде ничего сложного

```python3
def addTwoNumbers(head1, head2):
    result = 0
    reminder = 0
    multiplier = 1

    curr1 = head1
    curr2 = head2
    while(curr1 and curr2):
        val = (curr1.val + curr2.val + reminder)
        result += (val % 10) * multiplier

        multiplier *= 10
        reminder = val // 10

        curr1 = curr1.next
        curr2 = curr2.next

    curr = curr1 or curr2
    while(curr):
        val = curr.val + reminder
        result = (val % 10) * multiplier + result

        multiplier *= 10
        reminder = val // 10
        curr = curr.next

    if reminder > 0:
        result = reminder * multiplier + result

    return result
```

Второй вариант:
```python3
def addTwoNumbers(head1, head2):
    result = 0
    reminder = 0
    multiplier = 1

    while(head1 or head2):
        val = reminder
        
        if head1:
            val += head1.val
            head1 = head1.next
        
        if head2:
            val += head2.val
            head2 = head2.next
        
        result += (val % 10) * multiplier

        multiplier *= 10
        reminder = val // 10

    result += reminder * multiplier

    return result
```

Решение которое увидел на просторах интернета:
Идея: так как на выходе нам нужно число а не список мы можем сделать так:
Прошлись по первому списку собрали число.
Прошлись по второму списку собрали число.
Вернули сумму.
```python3
def sumTwoLists(head1, head2):
    n1 = listToInt(head1)
    n2 = listToInt(head2)
    
    return n1 + n2
    
def listToInt(head):
    result = 0
    multiplier = 1
    
    while(head):
        result += head.val * multiplier
        multiplier *= 10
        head = head.next
 
    return result
```
