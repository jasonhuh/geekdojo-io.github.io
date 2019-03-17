---
layout: post
title: Programming Challenges - Week 4 - Review Competition Problems
---

### Review problems

- Teamscode - Spring 2019 MIHS

### Data Structure and Algorithms

#### Big O Notation

The Big O (pronounced 'Oh') notation is used to classify algorithms according to how its running time or space requirements 
grow as the input size grows (very big, like millions and billions).

#### Data Structure

- Primitive Types
- Array
- Linked List
- Hash Table (Dictionary)
- Stack and Queue
- Tree
- Heap
- Graph

#### Data Structure: Linked List

Contiguous vs. Linked Data Structures

- Contiguously allocated structures: arrays, heaps, and hash tables
- Linked data structures: lists, trees, and graph adjacency lists

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
```

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
