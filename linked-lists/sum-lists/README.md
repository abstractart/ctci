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
        if head1: val += head1.val
        if head2: val += head2.val
        
        result += (val % 10) * multiplier

        multiplier *= 10
        reminder = val // 10

        if head1.next: head1 = head1.next
        if head2.next: head2 = head2.next

    result += reminder * multiplier

    return result
```
