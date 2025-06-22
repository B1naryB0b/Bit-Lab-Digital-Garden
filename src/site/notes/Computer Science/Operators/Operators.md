---
{"dg-publish":true,"permalink":"/computer-science/operators/operators/","tags":["nooblet","unfinished"],"noteIcon":"1"}
---

```ad-tldr
Basically all the simple maths and logicky bits that make stuff work.
```

Operators are a set of symbols that represent a specific mathematical or logical operation. They follow a [[Computer Science/Operators/Operator Precedence\|order of operations]] when the application is being run to determine which operator is executed first and which are next.

```ad-tip
**When you are starting out, don't feel the need to memorise every operator.** You will likely only use [[Arithmetic Operators|arithmetic]], [[Comparison Operators|comparison]] and [[Logical Operators|logical operators]].

**It is also perfectly normal to constantly reference a list of operators** like this at first. The more you make use of them, the less you will need reference, but even experienced developers will check for some of the more obscure operators.
```
# [[Computer Science/Operators/Arithmetic Operators\|Arithmetic Operators]] 


<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/computer-science/operators/arithmetic-operators/#arithmatic-ops" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">



| Name           | Maths        | [[Computer Science/Operators/Operators\|Operator]] | Example  | Note                                                                                          |
| -------------- | ------------ | ----------------------- | -------- | --------------------------------------------------------------------------------------------- |
| Addition       | $x + y$      | `+`                     | `x + y`  |                                                                                               |
| Subtraction    | $x - y$      | `-`                     | `x - y`  |                                                                                               |
| Multiplication | $x \times y$ | `*`                     | `x * y`  |                                                                                               |
| Division       | $x \div y$   | `/`                     | `x / y`  | Division by zero will throw an exception.                                                     |
| Modulus        | $x \bmod y$  | `%`                     | `x % y`  | Returns remainder of division.                                                                |
| Exponentiation | $x^y$        | `**`                    | `x ** y` | In [[Software Development/Programming Languages/C Sharp\|C#]] , use `Math.Pow(x, y)` for exponentiation as `**` is not a valid operator. |

</div></div>


# [[Computer Science/Operators/Comparison Operators\|Comparison Operators]] 


<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/computer-science/operators/comparison-operators/#comparison-ops" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">



| Name             | Maths      | [[Computer Science/Operators/Operators\|Operator]] | Example  | Note                      |
| ---------------- | ---------- | ----------------------- | -------- | ------------------------- |
| Equal to         | $x = y$    | `==`                    | `x == y` | Allows for type coercion. |
| Not equal to     | $x \neq y$ | `!=`                    | `x != y` | Allows for type coercion. |
| Greater than     | $x > y$    | `>`                     | `x > y`  |                           |
| Less than        | $x < y$    | `<`                     | `x < y`  |                           |
| Greater or equal | $x \geq y$ | `>=`                    | `x >= y` |                           |
| Less or equal    | $x \leq y$ | `<=`                    | `x <= y` |                           |

</div></div>



# [[Computer Science/Operators/Logical Operators\|Logical Operators]] 


<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/computer-science/operators/logical-operators/#logical-ops" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">



| Name        | Maths    | [[Computer Science/Operators/Operators\|Operator]] | Example    | Note                                          |
| ----------- | -------- | ----------------------- | ---------- | --------------------------------------------- |
| Logical NOT | $\neg$   | `!`                     | `!x`       | Inverts the boolean value.                    |
| Logical AND | $\wedge$ | `&&`                    | `x && y`   | Returns true if both operands are true.       |
| Logical OR  | $\lor$   | `\|\|`                  | `x \|\| y` | Returns true if at least one operand is true. |
| Logical XOR | $\oplus$ | `^`                     | `x ^ y`    | Returns true if operands are different.       |

</div></div>



# [[Computer Science/Operators/Assignment Operators\|Assignment Operators]] 


<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/computer-science/operators/assignment-operators/#assignment-ops" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">



| Name                                      | Maths            | [[Computer Science/Operators/Operators\|Operator]] | Example   | Note                                      |
| ----------------------------------------- | ---------------- | ----------------------- | --------- | ----------------------------------------- |
| Simple assignment                         | $x = y$          | `=`                     | `x = y`   |                                           |
| Addition assign                           | $x = x + y$      | `+=`                    | `x += y`  |                                           |
| Subtraction assign                        | $x = x - y$      | `-=`                    | `x -= y`  |                                           |
| Multiplication assign                     | $x = x \times y$ | `*=`                    | `x *= y`  |                                           |
| Division assign                           | $x = x \div y$   | `/=`                    | `x /= y`  | Division by zero will throw an exception. |
| Modulus assign                            | $x = x \bmod y$  | `%=`                    | `x %= y`  |                                           |
| [[Computer Science/Operators/Bitwise Operators\|Bitwise]] AND assign | $x = x \land y$  | `&=`                    | `x &= y`  |                                           |
| [[Computer Science/Operators/Bitwise Operators\|Bitwise]] OR assign  | $x = x \lor y$   | `\|=`                   | `x \|= y` |                                           |
| [[Computer Science/Operators/Bitwise Operators\|Bitwise]] XOR assign | $x = x \oplus y$ | `^=`                    | `x ^= y`  |                                           |
| Left shift assign                         | $x = x << n$     | `<<=`                   | `x <<= n` |                                           |
| Right shift assign                        | $x = x >> n$     | `>>=`                   | `x >>= n` |                                           |

</div></div>



# [[Computer Science/Operators/Bitwise Operators\|Bitwise Operators]] 


<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/computer-science/operators/bitwise-operators/#bitwise-ops" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">



| Name                 | Maths    | [[Computer Science/Operators/Operators\|Operator]] | Example   | Note                                                                                       |
| -------------------- | -------- | ----------------------- | --------- | ------------------------------------------------------------------------------------------ |
| Bitwise NOT          | $\neg$   | `~`                     | `~x`      | Inverts all the bits.                                                                      |
| Bitwise AND          | $\land$  | `&`                     | `x & y`   | Sets each bit to 1 if both bits are 1.                                                     |
| Bitwise OR           | $\lor$   | `\|`                    | `x \| y`  | Sets each bit to 1 if one of the bits is 1.                                                |
| Bitwise XOR          | $\oplus$ | `^`                     | `x ^ y`   | Sets each bit to 1 if only one of the bits is 1.                                           |
| Left Shift           |          | `<<`                    | `x << n`  | Shifts the bits of x to the left by n places.                                              |
| Right Shift          |          | `>>`                    | `x >> n`  | Shifts the bits of x to the right by n places.                                             |
| Unsigned Right Shift |          | `>>>`                   | `x >>> n` | Shifts the bits of x to the right by n places (zero fill). Not available in all languages. |

</div></div>



https://www.tutorialspoint.com/csharp/csharp_operators.htm