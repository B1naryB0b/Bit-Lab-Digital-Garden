---
{"dg-publish":true,"permalink":"/computer-science/programming/parameters-and-arguments/","tags":["beginner"]}
---

# Parameters 

**Parameters are input [[Computer Science/Variables/Variables\|variables]] for our [[Computer Science/Programming/Methods\|function]]/[[Computer Science/Programming/Methods\|method]].**  When we create a [[Computer Science/Programming/Methods\|method]], we also tell it what parameters it should use. These act like **placeholder values of the same type**, so when an argument is passed to the [[Computer Science/Programming/Methods\|method]] it uses the real values given by the argument when running the [[Computer Science/Programming/Methods\|method]].

```csharp
public void PrintSum(int a, int b)
{
	int sum = a + b;
	Console.WriteLine($"Sum total: {sum}");
}
```

In this case the parameters `a` and `b` are used as placeholders for any operations done within the [[Computer Science/Programming/Methods\|method]].

# Arguments 

These are the values passed onto the [[Computer Science/Programming/Methods\|method]]. For instance, if we invoked the `PrintSum()` [[Computer Science/Programming/Methods\|method]]:

```csharp
//Pass in arguments
PrintSum(5, 10)
```
```output
Sum total: 15
```

In this case the arguments were the numbers `5` and `10`, but they can be any [[Computer Science/Variables/Variables\|variable]] of the same type as the parameter.

# Optional Parameters  

These are parameters that don't need to be included in the [[Computer Science/Programming/Methods\|method]] call and have arguments passed to them. They are given a default value if an argument isn't provided and must be placed after all required parameters.

```csharp
public void PrintSum(int a, int b, int c = 0)
{
	int sum = a + b + c;
	Console.WriteLine($"Sum total: {sum}");
}
```

In this case the parameter `c` has a default value of `0`, so if no argument is provided, it will use the default value.

```csharp
//Pass in all arguments
PrintSum(5, 10, 15)
//Pass in only required arguments
PrintSum(5, 10)
```
```output
Sum total: 30
Sum total: 15
```

# References

https://code-maze.com/csharp-methods/