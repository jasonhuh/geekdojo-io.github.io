---
layout: post
title: Programming Challenges - Week 4 - Review Competition Problems and Intro to Data Structure
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

Let's try a Jupyter notebook. Here are key operations:
- Press `Shift + Enter` to execute a cell.

##### Loading a matplot libary

Add the following code in the Jupyter notebook, and press `Shift + Enter`.

```py
%matplotlib inline
import math
import matplotlib.pyplot as plt
```

Add the following code on the second cell and press `Shift + Enter`.

```py
N = 1000000 # 1 million
```

Add the rest of the code and the third cell and press `Shift + Enter`.

```py
a = [i for i in range(1, N)]  # O(N)
b = [i*i for i in range(N)] # O(N^2)
c = [math.log(i) for i in range(100, N)] # O(log(N))
d = [i * math.log(i) for i in range(100, N)] # O(N*log(N))
plt.ylabel('Time')
plt.xlabel('Size of input')
plot_a, = plt.plot(a, color='blue', label='O(N)')
plot_b, = plt.plot(b, color='red', label='O(N^2)')
plot_c, = plt.plot(c, color='purple', label='O(log(N))')
plot_d, = plt.plot(d, color='green',  label='O(N*log(N))')
plt.legend(handles=[plot_a, plot_b, plot_c, plot_d], loc=1)
plt.show()
```

Here are the results. The higher the time (y-axis), the slower the runtime is.

![Big O](/images/big_o_1.png)

![Big O](/images/big_o_2.png)

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

##### Summary

We learned the basic concept of Big O notation, and studied the characteristics of different running time using Jupyter Notebook (which is way cool!). 
