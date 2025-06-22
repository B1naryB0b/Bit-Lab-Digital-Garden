---
{"dg-publish":true,"permalink":"/computer-science/variables/booleans/","tags":["nooblet","beginner","unfinished"],"noteIcon":"1"}
---


# Bools

A Boolean or bool is **a true or false value, sometimes denoted through a 1 or 0, and is used to make logical statements.**[^1] Normally you can convey this information in 1 bit, however due to practical reasons computers operate in 1 byte chunks so a `bool` is 1 byte in [[Computer Science/Hardware/RAM\|memory]].[^2]

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

# Footnotes

[^1]: https://www.w3schools.com/cs/cs_booleans.php 
[^2]: https://stackoverflow.com/questions/8014161/in-c-how-much-space-does-a-bool-boolean-take-up-is-it-1-bit-1-byte-or-someth
