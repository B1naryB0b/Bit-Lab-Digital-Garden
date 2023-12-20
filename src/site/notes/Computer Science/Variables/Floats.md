---
{"dg-publish":true,"permalink":"/computer-science/variables/floats/","tags":["nooblet","beginner"]}
---


<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/computer-science/variables/variables/#floats" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">



# Floats

A floating point number or float, depending on the language, is generally 32 bits / 4 bytes of [[Computer Science/Binary\|machine code]] used to represent a signed (meaning including negative) decimal number. It gets it's name from the fact that after the sign bit, the next five bits are used to denote the exponent of the number or where the decimal point is, hence floating point. The significand is a sum of fractions where the first bit is $\frac{1}{2}$ and each subsequent bit is half of the one that came before it (e.g. $\frac{1}{2} + \frac{1}{4} + \frac{1}{8} + \frac{1}{16}... \frac{1}{1024}$).

![floating_point_4_darkcolor.006.webp](/img/user/floating_point_4_darkcolor.006.webp)

This way of storing numbers allows you to reach 7 decimal digits of precision within a massive range using only 32 bits / 4 bytes of [[Computer Science/Hardware/RAM\|memory]].[^2]

```csharp
//These are valid integers (some languages use f suffix to denote floats)
float mols = 12.14f;
float avagadroConstant = 6.022E23f;
float boltzmannConstant = 1.380649f * Mathf.Pow(10, -23);

//These are invalid or inaccurate as they are not decimal values or are out of range
float plancksConstant = 6.62607015E-34f; //You lose 1 decimal digit of accuracy
float thisIsNotAFloat = "This is not a float";
```

For instance in [[IRL Programming/Programming Languages/C Sharp\|C#]] and [[IRL Programming/Programming Languages/Java\|Java]] a `float` can represent values in the range:

```csharp
float max = float.MaxValue;
float min = float.MinValue;

Console.WriteLine($"Range of float: {min} to {max}");
```
```output
Range of float: -3.402823E+38 to 3.402823E+38
```

> [!tip]
> Because floats can be used to represent a massive range of values, it is better to think of them in terms of decimal digits of precision rather than in terms of size.
## Doubles

>When two floats love each other very much they combine like something out of an anime.
>-Me

Basically an extra long float with double the digits for precision.


</div></div>


