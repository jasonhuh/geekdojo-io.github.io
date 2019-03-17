---
layout: post
title: Programming Challenges - Week 4 - Review Competition Problems
---

### Review problems


### Data Structure and Algorithms

#### Data Structure

- Primitive Types
- Array
- Linked List
- Hash Table (Dictionary)
- Stack and Queue
- Tree
- Graph

#### Data Structure: Linked List

```py
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None
        
head = Node(1)
head.next = Node(2)
head.next.next = Node(3)
```

##### Linked List: Insert

```py
def insert(head, data):
    tmp = Node(data)
    tmp.next = head.next
    head = tmp
```

##### Linked List: Search

```py
def search(head, data):
    tmp = head
    while tmp:
        if tmp.data == data:
            break
        tmp = tmp.next
    return tmp

##### Linked List: Delete

```py
def delete(node_to_delete):
    node_to_delete.data = node_to_delete.next.data
    node_to_delete.next = node_to_delete.next.next
```

##### Linked List: Print all nodes

```py
def print_linked_list(head):
    tmp = head
    while tmp:
        print(tmp.data, end=' ')
        tmp = tmp.next
```
