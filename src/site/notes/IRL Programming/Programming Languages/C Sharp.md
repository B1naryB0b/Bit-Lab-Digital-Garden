---
{"dg-publish":true,"permalink":"/irl-programming/programming-languages/c-sharp/","tags":["unfinished"]}
---

> [!tldr]
> 

If you want a more technical overview of the language check out [Microsoft's tour of c#](https://learn.microsoft.com/en-us/dotnet/csharp/tour-of-csharp/).
# Features

## Lists and Linked Lists 

In C# lists and [[Computer Science/Data Structures/Linked List\|linked lists]] have different performance characteristics. Whilst a `LinkedList<T>` behaves the same as... well, a [[Computer Science/Data Structures/Linked List\|linked list]]. A `List<T>` in C# is actually an internally backed array under the hood. This allows `List<T>` to be fast for access by index and can cheaply add/remove at the end of the list due to its wrapper, but removing or inserting elements at the start or within the list is costly.

[Stack Overflow: Difference between List and LinkedList](https://stackoverflow.com/questions/4279020/difference-between-listt-and-linkedlistt)

## Explicit Access Modifiers

In C# you can't group access modifiers like you do in some other languages. This makes it a bit longer to write, but means that you won't introduce strange bugs in your code by moving a variable or have to scroll to the top to see which access modifier you are using.

For instance in C++ you can group access modifiers like `public` and `private`.
```cpp
public:
	float distance;
	float speed;

private:
	float time;
```

In C# you are required to explicitly declare the access modifier. Although C# automatically defaults to `private` if you don't provide an access modifier it is **HIGHLY** advised that you write it explicitly to prevent confusion.
```csharp
public float distance;
public float speed;

private float time;
```
# Syntax
