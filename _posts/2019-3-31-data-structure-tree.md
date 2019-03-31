---
layout: post
title: Programming Challenges - Week 5 - Data Structure - Linked List (Cont.) and Tree
---

## Review problems

#### Homework (Hackeerank)
- Modular programming

## Linked List

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

```
##### Practice

1. Implement the `print_list` method that traverses each node recursively and print its value

```py
def print_list(node):
    pass
```

2. Write a function return the length of a linked list.
```py
def length_of_list(head):
    pass
```

3. Write a function to determin if a linked list contains a duplicate value
```py
def has_duplicate(head):
    pass
```


## Tree

### Binary Tree

```py
class Node:
    def __init__(self, val):
        self.left = None
        self.right = None
        self.val = val        
```

#### Traverse through Tree

<pre>
        4
      /   \
     2     5
   /  \     \
  1    3     6
</pre>

##### Let's traverse!

```py
root = Node(4)
root.left = Node(2)
root.left.left = Node(1)
root.left.right = Node(3)
root.right = Node(5)
root.right.right = Node(6)

def traverse(node):
    if not node:
        return
    traverse(node.left)
    print(node.val)
    traverse(node.right)
    
traverse(root)

```
The above technique is called `Inorder Traversal`, and the tree is called `Binary Search Tree` 
where the left subtree of a node contains only nodes with keys smaller than the node's key, and the right subtree of
a node contains nodes with keys bigger than the node's key.

