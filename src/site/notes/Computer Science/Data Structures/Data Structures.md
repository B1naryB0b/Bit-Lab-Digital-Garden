---
{"dg-publish":true,"permalink":"/computer-science/data-structures/data-structures/","tags":["beginner","unfinished"]}
---


> [!tldr]
> A data structure is just a way of storing and organising data so it can be used efficiently. **That's it.**
> 
> The difficult of data structures comes from picking the right one for your use case and learning techniques to make the most of the data structure you pick.

# Primitive

These are [[Computer Science/Variables/Variables\|variable]] data types that act as the **building blocks of data structures.** They are chained or allocated in groups to create any of the more complex objects like [[Computer Science/Data Structures/Array\|arrays]] or [[Computer Science/Data Structures/Linked List\|lists]] and many others.

Primitive data structures includes stuff like:
- [[Computer Science/Variables/Booleans\|Booleans]]
- [[Computer Science/Variables/Integers\|Integers]]
- [[Computer Science/Variables/Floats\|Floats]]
- [[Computer Science/Variables/Characters\|Characters]]
- [[Computer Science/Variables/Strings\|Strings]]
- [[Computer Science/Variables/Pointers\|Pointers]]

# Non-primitive

Non-primitive data structures fall into two camps, linear and non-linear.
## Linear

These are data structures that are arranged in sequence, one after the other like [[Computer Science/Data Structures/Array\|arrays]], [[Computer Science/Data Structures/Stack\|stacks]] or [[Computer Science/Data Structures/Queue\|queues]]. They are often quite simple and intuitive, and although they are more simple to implement, their **time complexity scales with the amount of data they are holding.**

This simplicity comes from the **elements all being on a single layer** you can iterate through, this also means that **we can traverse the entire data structure sequentially in a single pass.**

```python
# Define an array with some values
numbers = [1, 2, 3, 4, 5]

# Iterate through the array and print each value
for number in numbers:
    print(number)
```

You can see that as the number of elements increases the time complexity also increases significantly. Especially once we start iterating over 2D or higher order linear data structures we get $O(n^{2})$ [[Computer Science/Complexity/Time Complexity\|time complexity]].

```python
# Define a 2D array (list of lists) with some values
numbers = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]

# Iterate through the 2D array and print each value
for row in numbers:
    for number in row:
        print(number)

```

## Non-linear

These are data structures that are **arranged in a hierarchy where a [[Computer Science/Data Structures/Nodes\|node]] containing an element is connected to one or more other [[Computer Science/Data Structures/Nodes\|nodes]].** They are not arranged in any particular sequence which makes them more difficult to implement and requires multiple passes to traverse the entire data structure. However, **their [[Computer Science/Complexity/Time Complexity\|Time Complexity]] tends to remain constant even when working with large amounts of data** making them much more efficient for large scale applications.

For instance in something like the graph shown below its not possible for you to do a single pass (shown in purple) to traverse the entire structure. **You must do multiple passes to search the entire data structure.**

![Non-linear Data Structure (Graph).excalidraw.png](/img/user/Excalidraw/Data%20Structures/Non-linear%20Data%20Structure%20(Graph).excalidraw.png)