---
layout: post
title: Programming Challenges - Week 4 - Review Competition Problems
---

### Review problems

- Teamscode - Spring 2019 MIHS

### Practice blogging

- Create a new blog
- Review Markdown
- Add image

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

![Array vs. Linked List, Trees and Graphs](/images/data_structure_overview.jpg)

#### Data Structure: Linked List

Contiguous vs. Linked Data Structures

- Contiguously allocated structures: arrays, heaps, and hash tables
- Linked data structures: lists, trees, and graph adjacency lists

```py
class Node:
    """
    Node for Linked List
    """
    def __init__(self, data: int):
        self.data = data
        self.next = None
        
head = Node(1)
assert head.data == 1
```

##### Linked List: Insert

```py
def insert(node, data: int):
    """
    Insertion at the beginning to avoid
    traversing the list
    """
    tmp = Node(data)
    tmp.next = node
    node = tmp
    return node

head = Node(1)
assert head.data == 1

head = insert(head, 2)
assert head.data == 2
assert head.next.data == 1    
```

##### Linked List: Find

There are two ways to implement the `find` method -- recursively or iteratively. In either case, 
it takes *O(N)* time to find an item in a linked list.

```py
# Recursive find
def find_recursive(node, data):
    """
    Recursively traverse the list and
    return a node when its data mathes a provided data
    """
    if node is None:
        return
    if node.data == data:
        return node
    return find_recursive(node.next, data)
```

```py
def find(head, data):
    """
    Find a node iteratively for a provided data
    """
    tmp = head
    while tmp:
        if tmp.data == data:
            break
        tmp = tmp.next
    return tmp

head = Node(1)
assert head.data == 1

head = insert(head, 2)
assert head.data == 2
assert head.next.data == 1

head = insert(head, 3)
print_list(head)

assert find(head, 7) == None
assert find(head, 3) == head
assert find(head, 2) == head.next    
```

##### Linked List: Delete

Deletion is more complicated than other operations. First, we need to find a pointer to the predecessor of 
the item to be deleted. 

```py
def find_predecessor(node, data):
    """
    Find a predecessor of a node of which data matches a provided data
    """
    if node is None or node.next is None:
        return
    if node.next.data == data:
        return node
    else:
        return find_predecessor(node.next, data)
```        

We needed the predecessor so that its _next_ pointer must be changed.

```py
def delete(head, data):
    """
    Deleting a node requires a pointer to a predecessor
    """
    cur = find_recursive(head, data)
    if cur:
        pred = find_predecessor(head, data)
        if pred is None:
             head = cur.next
        else:
            pred.next = cur.next
    return head
```

##### Linked List: Print all nodes

```py
def print_list(node):
    """
    Recursively traverse the list and
    print data
    """
    if node is None:
        return
    print(node.data, end=' ')
    print_list(node.next)
```

##### Putting all together

Here is the code for the above operations of a linked list.
{% gist 69634f61bd4234214893a38746934a96 %}


##### Summary

Linked List is a our first step to learn a linked data structure that is different from a contiguous data structure such as an array. The concept and techniques learend in Linked List are the building blocks for other data structure such as lists, trees and graphs.
