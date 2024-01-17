---
{"dg-publish":true,"permalink":"/computer-science/variables/booleans/","tags":["nooblet","beginner","unfinished"]}
---


# Bools

A Boolean or bool is **a true or false value, sometimes denoted through a 1 or 0, and is used to make logical statements.** Normally you can convey this information in 1 bit, however due to practical reasons computers operate in 1 byte chunks so a `bool` is 1 byte in [[Computer Science/Hardware/RAM\|memory]].

For instance you can make conditional statements like the following using logical operators:
```csharp
bool isProgrammingFun = true;
bool isCodeBugged = false;

if (isProgrammingFun && !isCodeBugged)
{
	Console.WriteLine("Look at how fun programming is!")
}
else
{
	Console.WriteLine("Time to jump off a bridge!")
	//JK, please don't jump off a bridge
}
```
```output
Look at how fun programming is!
```