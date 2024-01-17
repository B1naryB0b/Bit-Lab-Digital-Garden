---
{"dg-publish":true,"permalink":"/computer-science/data-structures/array/","tags":["unfinished"]}
---

An array is a collection of primitive [[Computer Science/Variables/Variables\|variables]] that allows you to use some standard manipulations, on a large group of data. 

# Using Arrays

## 1D Arrays

A 1D array is the most simple form of a collection of primitive [[Computer Science/Variables/Variables\|variables]]. For instance:
```csharp
// Array of heights in cm
int[] heights = new int[] { 170, 183, 165, 165, 175, 170 };

// Array of names
string[] names = new string[] { "Tim", "Elanor", "Isaac", "Ali", "Charles" };
```

These can be made of any type of primitive data type and in some cases more complex data types depending on your use case.

## Higher Dimensional Arrays

These are essentially arrays within arrays, if you have one array nested within another then it is a 2D array, if you have another nested within each of those then it is a 3D array and so on and so forth. You might need an n-dimensional array for some tasks although in many cases another data structure might prove to be more suitable.

```csharp
// Array of heights in the form [height(cm), frequency]
int[,] heights = new int[,] 
{
    { 170, 2 },
    { 183, 1 },
    { 165, 2 },
    { 175, 1 }
};

// Array of names in the form [firstname, lastname]
string[,] names = new string[,]
{
    { "Tim", "Cook" },
    { "Elanor", "Roosevelt" },
    { "Issac", "Newton" },
    { "Ali", "Baba" },
    { "Charles", "Xavier" }
};
```

The reason another structure might be more suitable in some cases is that the time complexity of all data manipulations increase significantly with 
# Arrays in Memory

Let's look at how these manipulations work and how arrays are stored in [[Computer Science/Hardware/RAM\|memory]].

```csharp
// Define an array with some values
int[] numbers = new int[] { 1, 2, 3, 4 };
```

This array is stored in [[Computer Science/Hardware/RAM\|memory]] sequentially with each integer being assigned to a memory location. This allows us to easily iterate over the array as the next item in the array is just one memory location over from the last one.

## Accessing

An arrays lookup speed doesn't depend on the size of the array. For instance:

```csharp
//Iterating through the array index
int[] numbers = new int[] { 1, 2, 3, 4 };

for (int i = 0; i < numbers.Length; i++)
{
    Console.WriteLine(numbers[i]);
}
```

In this code we are accessing each number in the array by index. Because we know the memory location of the array we just need to go to however many memory locations along depending on the index. When we access `numbers[2]` all we have to do is a single command with constant [[Computer Science/Complexity/Time Complexity\|time complexity]] (or $O(1)$ time), which is `numbers_memory_address + (memory_size * index)`.

![Array in Memory.excalidraw.png|1080](/img/user/Excalidraw/Array%20in%20Memory.excalidraw.png)

## Searching
#unfinished

## Pushing

```csharp
int[] numbers = new int[] { 1, 2, 3, 4 };

// Resize the array and append the new empty element
Array.Resize(ref numbers, numbers.Length + 1);
// Places the number 5 in array index 4 memory location
numbers[numbers.Length - 1] = 5;
```

However, when we push a value to the array, we are forced to move the entire array to a different memory location as the value in that memory location might already be occupied by another piece of data.

![Array Memory Allocation.excalidraw.png|1080](/img/user/Excalidraw/Array%20Memory%20Allocation.excalidraw.png)

## Popping

```csharp
int[] numbers = new int[] { 1, 2, 3, 4 };

// Check if the array is not empty
if (numbers.Length > 0)
{
    // Create a new array with one less slot
    int[] smallerNumbers = new int[numbers.Length - 1];

    // Copy the original array to the new array, excluding the last element
    Array.Copy(numbers, smallerNumbers, numbers.Length - 1);

    // Assign the new array back to numbers
    numbers = smallerNumbers;
}
```

Removing an element 

![Array Memory Deallocation.excalidraw.png|1080](/img/user/Excalidraw/Array%20Memory%20Deallocation.excalidraw.png)

In some languages like [[IRL Programming/Programming Languages/Python\|python]] you can't create arrays without using a library like NumPy.