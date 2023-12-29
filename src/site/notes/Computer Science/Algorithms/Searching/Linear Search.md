---
{"dg-publish":true,"permalink":"/computer-science/algorithms/searching/linear-search/"}
---

A linear search simply iterates through every element in a [[Computer Science/Data Structures/Data Structures#Linear\|linear data structure]]. For instance:

```csharp
//Example data
int[] numbers = {4, 2, 1, 8, 7, 9, 4, 2, 4};
int targetNumber = 2;

Console.WriteLine($"My target number is: {targetNumber}");

//Linear search
for (int i = 0, i < numbers.Length, i++)
{
	if(numbers[i] == targetNumber)
	{
		Console.WriteLine($"Target number found at index: {numbers[i]}");
	}
}
```
```output
My target number is: 2
Target number found at index: 1
Target number found at index: 7
```

 A linear search checks each element in a dataset sequentially until it finds the desired element. Its main disadvantage is its slow speed for large datasets due to its $O(n)$ time complexity, meaning search time doubles with list size.