---
{"dg-publish":true,"permalink":"/computer-science/variables/variables/","tags":["nooblet","beginner"]}
---

# Ints

Ints are stored differently depending on the language, but are generally **32 bits / 4 bytes** of [[Computer Science/Binary\|machine code]] **used to represent a signed (meaning including negative) whole number.** You can't store decimal values or factions with it (unless the fractions simplify to whole numbers).

```csharp
//These are valid integers
int population = 100
int populationGrowth= -3

//These invalid as they are not whole numbers
int averageAge = 35.4
int averageTestScore = 14/20
```

For instance in [[IRL Programming/Programming Languages/C Sharp\|C#]] or [[IRL Programming/Programming Languages/Java\|Java]] an `int` can represent values in the range:
```csharp
int max = int.MaxValue;
int min = int.MinValue;
Console.WriteLine($"Range of int: {min:N0} to {max:N0}");
```
```output
Range of int: -2,147,483,648 to 2,147,483,647
```

For some languages the size of an `int` is determined by the [[Computer Science/Complier\|compiler]] such as with C++ or is machine dependent like in Swift. There are even some languages like [[IRL Programming/Programming Languages/Python\|Python]] where there is no limit on the range of integers it can store[^1].

## Short

In some rare cases you might *need* to save [[Computer Science/Hardware/RAM\|memory]] or improve the performance of a particular function. In that case you have the `short`, **16 bits / 2 bytes** of [[Computer Science/Binary\|machine code]] that work the same as an `int` but can only store numbers in the range:
```csharp
short max = short.MaxValue;
short min = short.MinValue;
Console.WriteLine($"Range of short: {min:N0} to {max:N0}");
```
```output
Range of short: -32,768 to 32,767
```

```ad-warning
It is only feasible to make use of a `short` when working at low integer ranges as you are much more likely to hit an [[Overflow Error|overflow error]].

Also note that this is a micro optimisation and in most instances you should just stick with using an `int`. 

Your time is more valuable than your computers.
```

## Long

A `long` is far more likely to have practical applications, especially when working with very large numbers. It is **64 bits / 8 bytes** of [[Computer Science/Binary\|machine code]] that stores signed whole numbers in the absurdly large range:
```csharp
long max = long.MaxValue;
long min = long.MinValue;
Console.WriteLine($"Range of long: {min:N0} to {max:N0}");
```
```output
Range of long: -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807
```

This can have uses when working with very large numbers although it does take up double the [[Computer Science/Hardware/RAM\|memory]] of an `int`so can be quite costly if used in large [[Computer Science/Data Structures/Data Structures\|data structures]].

## Unsigned

So far all of the integers we've looked at are signed and can have a positive or negative value. If you are looking at a specific case where you won't be using negative numbers then you can use the unsigned variants of `int`, `short` and `long`.

These are `uint`, `ushort` and `ulong` which trade the bit used for denoting a positive or negative integer with doubling the upper limit of the range. Compare the ranges of `uint` and `int`:
```csharp
int max = int.MaxValue;
int min = int.MinValue;
Console.WriteLine($"Range of int: {min:N0} to {max:N0}");
```
```output
Range of int: -2,147,483,648 to 2,147,483,647
```

```csharp
uint max = uint.MaxValue;
uint min = uint.MinValue;
Console.WriteLine($"Range of uint: {min:N0} to {max:N0}");
```
```output
Range of uint: 0 to 4,294,967,295
```

```ad-warning
It is not recommended to use unsigned integer in most cases as they are not [CLS-Compliant](https://learn.microsoft.com/en-us/previous-versions/visualstudio/visual-studio-2008/bhc3fa7f(v=vs.90)?redirectedfrom=MSDN). They only make sense when you are doing [[Bitwise Operations|bitwise operations]] or are desperate to take advantage of that extra positive range.
```

# Floats

A floating point number or float is a N-bit representation of a number, it gets it's name from the fact that the first x-bits are used to denote the sign of the number and the position of its decimal point, thus allowing it to offer a massive breath of possible values without overloading it's memory budget.
## Doubles

>When two floats love each other very much they combine like something out of an anime.
>-Me

Basically an extra long float with double the digits for precision.

# Bools

A Boolean or bool is a true or false value, sometimes denoted through a 1 or 0.

# Chars

A character or char is an N-bit representation of an ASCII letter or number. These characters can't be modified with a mathematical operator.
## Strings

A string is an array of characters that has some additional functionality to allow for concatenation and modification of 

>Wait... so it's just an array of characters in a trench coat?
>-Me

# Pointers

A pointer is a way of referencing an address in memory, hence the name pointer, it is literally pointing at another memory address.

Pointers are a way to reference something without having to recompute it.

# Consts



# Footnotes

[^1]: https://press.rebus.community/programmingfundamentals/chapter/integer-data-type/