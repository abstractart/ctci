```python3
from typing import List


class Animal:
    def __init__(self, name) -> None:
        self.name = name

class Dog(Animal):
    pass

class Cat(Animal):
    pass


class Node:
    def __init__(self, value, next = None) -> None:
        self.value = value
        self.next = next



class LinkedList:
    def __init__(self) -> None:
        self.head = Node(0)
        self.tail = self.head

    def getHead(self):
        if not self.head.next:
            return None

        return self.head.next.value
    
    def appendToTail(self, value):
        self.tail.next = Node(value)
        self.tail = self.tail.next
    
    def popHead(self):        
        v = self.getHead()
        if not v:
            raise
        
        self.head.next = self.head.next.next

        return v


class DogsAndCats:
    def __init__(self) -> None:
        self.counter = 0
        self.dogs = LinkedList()
        self.cats = LinkedList()

    def enqueue(self, animal):
        v = (self.counter + 1, animal)

        if isinstance(animal, Dog):
            self.dogs.appendToTail(v)
        elif isinstance(animal, Cat):
            self.cats.appendToTail(v)
        
        self.counter += 1

    def dequeueAny(self):
        animals = []

        if self.dogs.getHead():
            animals.append(self.dogs.getHead())
        if self.cats.getHead():
            animals.append(self.cats.getHead())

        if not animals:
            raise

        animal = min(animals)[1]
        
        if isinstance(animal, Dog):
            self.dogs.popHead()
        elif isinstance(animal, Cat):
            self.cats.popHead()

        return animal

    
    def dequeueCat(self):
        return self.cats.popHead()[1]
    
    def dequeueDog(self):
        return self.dogs.popHead()[1]




l = DogsAndCats()

l.enqueue(Dog("Hatiko"))
l.enqueue(Cat("Boris"))


print(l.dequeueAny().name)
print(l.dequeueAny().name)
```
