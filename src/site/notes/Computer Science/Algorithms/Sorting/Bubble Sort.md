---
{"dg-publish":true,"permalink":"/computer-science/algorithms/sorting/bubble-sort/","tags":["nooblet","beginner","unfinished"],"noteIcon":"1"}
---

> [!tldr]
> A simple to implement [[Computer Science/Algorithms/Sorting/Sorting Algorithms\|sorting algorithm]] that swaps values until the largest value is found and does another pass in exactly the same way until 2nd, 3rd, 4th etc largest values are found and the list is sorted.

A bubble sort is generally considered the simplest type of [[Computer Science/Algorithms/Sorting/Sorting Algorithms\|sorting algorithm]] and works by swapping adjacent elements in an [[Computer Science/Data Structures/Array\|array]] (or [[Computer Science/Data Structures/Linked List\|linked lists]]) until the largest element is at the end of the [[Computer Science/Data Structures/Array\|array]], the largest element is then considered sorted and you start again from the left (beginning or [[Computer Science/Data Structures/Array\|array]]) and swap elements to the right until you find the second largest item. With enough passes you will eventually have a sorted [[Computer Science/Data Structures/Array\|array]] at the end of it.

(Insert diagrams here)
# Implementation

This is an [[Computer Science/Algorithms/Sorting/Bubble Sort#Full Implementation\|implementation]] in [[Software Development/Programming Languages/C Sharp\|C#]] the most important part of which is the bubble sort algorithm itself, that is comprised of a nested for loops that check the two adjacent elements in the array and swaps them if the first term is larger. 

It then repeats this process for all unsorted term (a bubble sort pass) until it reaches the end of the array and another element has been sorted. The outer loop repeats the bubble sort pass until the array is populated with sorted elements.

```csharp
static void PerformBubbleSort(int[] array)
{
	int n = array.Length;
	
	//Repeat the bubble sort pass
	for (int i = 0; i < (n - 1); i++)
	{
		//One bubble sort pass
		for (int j = 0; j < (n - i - 1); j++)
		{
			//Check adjacent terms
			if (array[j] > array[j + 1])
			{
				// Swap temporary and array[i]
				int temporary = array[j];
				array[j] = array[j + 1];
				array[j + 1] = temporary;
			}
		}
	}
}
```

# [[Computer Science/Complexity/Time Complexity\|Time Complexity]]

It terms of [[Computer Science/Complexity/Time Complexity\|time complexity]], it has an efficient best case scenario of $\Omega (n)$, but is not suitable for large data sets as its average and worst case [[Computer Science/Complexity/Time Complexity\|time complexity]] are $\Theta (n^{2})$ and $O(n^{2})$ respectively. 

# Appendix

## Full Implementation

```csharp
using System;

class BubbleSort
{
    static void Main(string[] args)
    {
	    //Our unsorted array
        int[] array = {64, 34, 25, 12, 22, 11, 90};
        Console.WriteLine("Original array: ");
        PrintArray(array);
        
        PerformBubbleSort(array);
        Console.WriteLine("\\nSorted array: ");
        PrintArray(array);
    }
    
	static void PerformBubbleSort(int[] array)
	{
		int n = array.Length;
		
		for (int i = 0; i < (n - 1); i++)
		{
			for (int j = 0; j < (n - i - 1); j++)
			{
				if (array[j] > array[j + 1])
				{
					// Swap temporary and array[i]
					int temporary = array[j];
					array[j] = array[j + 1];
					array[j + 1] = temporary;
				}
			}
		}
	}
	
    static void PrintArray(int[] array)
    {
        foreach (int element in array)
        {
            Console.Write(element + " ");
        }
        Console.WriteLine();
    }
}

```
```output
Original array: 64 34 25 12 22 11 90

Sorted array: 11 12 22 25 34 64 90
```
