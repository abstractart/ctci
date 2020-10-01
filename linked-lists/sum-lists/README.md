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

    curr1 = head1
    curr2 = head2
    while(curr1 or curr2):
        val = reminder
        if curr1: val += curr1.val
        if curr2: val += curr2.val
        
        result += (val % 10) * multiplier

        multiplier *= 10
        reminder = val // 10

        if curr1.next: curr1 = curr1.next
        if curr2.next: curr2 = curr2.next

    result += reminder * multiplier

    return result
```
