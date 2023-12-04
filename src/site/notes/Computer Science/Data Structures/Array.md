---
{"dg-publish":true,"permalink":"/computer-science/data-structures/array/"}
---

An array is a collection of primitive [[Computer Science/Data Structures/Variables\|variables]] that allows you to use some standard manipulations, like pop and push items, on a large group of data. Let's look at how these manipulations work and how arrays are stored in [[Computer Science/Hardware/RAM\|memory]].

# Arrays in Memory

```python
# Define an array with some values
numbers = [1, 2, 3, 4]
```

This array is stored in [[Computer Science/Hardware/RAM\|memory]] sequentially with each integer being assigned to a memory location. This allows us to easily iterate over the array as the next item in the array is just one memory location over from the last one.

## Push()

```python
#Appending just pushes a value to the end of the array
numbers.append(5)
```

However, when we push a value to the array, we are forced to move the entire array to a different memory location as the value in that memory location might already be occupied by another piece of data.


<div class="transclusion internal-embed is-loaded"><div class="markdown-embed">

$<div class="markdown-embed-title">

# 1080px

</div>



==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
0 
1 
2 
3 
4 
5 
6 
7 
'a' 
1 
2 
3 
4 
true 
42 
'q' 
'a' 
1 
2 
3 
4 
0 
1 
2 
3 
4 
5 
42 
'q' 
5 
6 
7 
false 
1 
2 
3 
4 
124 
125 
126 
127 
128 
5 
- 
- 
129 
130 
131 
Skip
8-123 
Push 
0 
1 
2 
3 
memory location 
array index 
memory location 
memory location 
0 
1 
2 
3 
array index 
4 
0 
1 
2 
3 
array index 
4 


</div></div>


## Pop()

```python
#Pop removes the last item in the array if no array index is given
numbers.pop()
```

In comparison removing an element is much less costly than adding one. We just deallocate the data at the memory location and don't need to duplicate the entire array.


<div class="transclusion internal-embed is-loaded"><div class="markdown-embed">

$<div class="markdown-embed-title">

# 480px

</div>



==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
0 
1 
2 
3 
4 
5 
6 
7 
'a' 
1 
2 
3 
4 
true 
42 
'q' 
'a' 
1 
2 
3 
- 
0 
1 
2 
3 
4 
42 
'q' 
5 
6 
7 
Pop 
0 
1 
2 
3 
memory location 
array index 
memory location 
0 
1 
2 
array index 
true 


</div></div>


In statically typed languages resizing an array might not be allowed, in that case you have to use a [[Computer Science/Data Structures/List\|list]] to achieve a similar functionality.

