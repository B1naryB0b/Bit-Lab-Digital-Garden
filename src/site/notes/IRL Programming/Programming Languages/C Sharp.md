---
{"dg-publish":true,"permalink":"/irl-programming/programming-languages/c-sharp/"}
---

```ad-tldr

```

If you want a more technical overview of the language check out [Microsoft's tour of c#](https://learn.microsoft.com/en-us/dotnet/csharp/tour-of-csharp/).
# Features

## Lists and Linked Lists 

In C# lists and [[Computer Science/Data Structures/Linked List\|linked lists]] have different performance characteristics. Whilst a `LinkedList<T>` behaves the same as... well, a [[Computer Science/Data Structures/Linked List\|linked list]]. A `List<T>` in C# is actually an internally backed array under the hood. This allows `List<T>` to be fast for access by index and can cheaply add/remove at the end of the list due to its wrapper, but removing or inserting elements at the start or within the list is costly.

[Stack Overflow: Difference between List and LinkedList](https://stackoverflow.com/questions/4279020/difference-between-listt-and-linkedlistt)

# Syntax
