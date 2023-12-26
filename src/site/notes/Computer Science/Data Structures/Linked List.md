---
{"dg-publish":true,"permalink":"/computer-science/data-structures/linked-list/"}
---

>[!warning]
> Not to be confused with a `List` as these are often arrays with a wrapper for fast dynamic resizing. 

A `Linked List` is a set of nodes where each node only points to the memory address of the next element on the list.

# Using Linked Lists

```ad-important
In most cases using `List<T>` in a range of languages will be fairly similar if you aren't adding or removing many elements. However, the benefits of using `LinkedList<T>` or equivalent in your language are that they drastically speed up functions which require adding or removing many elements in a short amount of time, especially since their push and pop times are $O(1)$ rather than $O(n)$ [[Time Complexity|time complexity]] .
```

If your language doesn't support an implementation of linked lists by default you can add it yourself by following the step below.
## Node Class

A fairly simple implementation for a structure like a linked list might look like the following:

```python
class Node:
	def __init__(self, data, next_node=None):
		self.data = data
		self.next_node = next_node
	
	def set_next_node(self, next_node):
		self.next_node = next_node
	
	def get_next_node(self):
		return self.next_node
	
	def get_data(self):
		return self.data
```

This implementation allows you to have a node that only points to the next node in the linked list. 

## Linking Nodes

This can be done by creating an instance of the node and assigning data to the node.

```python
node1 = Node(1)
node2 = Node(2)
node3 = Node(3)
```

Then we need to link `node1` to `node2` and `node2` to `node3`.

```python
node1.set_next_node(node2)
node2.set_next_node(node3)
```

## Traversing the Linked List

To traverse the linked list and print the values, you can start at `node1` and follow the `next_node` references:

```python
current_node = node1

while current_node:
    print(current_node.get_value())
    current_node = current_node.get_next_node()
```
```output
1
2
3
```

# Linked Lists in Memory
#unfinished 

![Linked List Remove Node.excalidraw.png](/img/user/Excalidraw/Linked%20List%20Remove%20Node.excalidraw.png)

![Linked List Add Node.excalidraw.png](/img/user/Excalidraw/Linked%20List%20Add%20Node.excalidraw.png)

