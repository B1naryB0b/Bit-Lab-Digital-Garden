---
{"dg-publish":true,"permalink":"/computer-science/operators/bitwise-operators/","tags":["beginner","intermediate","unfinished"],"noteIcon":"1"}
---

These are [[Computer Science/Operators/Operators\|operators]] that perform operations on the binary representations of integers and return an integer result.

| Name                 | Maths    | [[Computer Science/Operators/Operators\|Operator]] | Example   | Note                                                                                       |
| -------------------- | -------- | ----------------------- | --------- | ------------------------------------------------------------------------------------------ |
| Bitwise NOT          | $\neg$   | `~`                     | `~x`      | Inverts all the bits.                                                                      |
| Bitwise AND          | $\land$  | `&`                     | `x & y`   | Sets each bit to 1 if both bits are 1.                                                     |
| Bitwise OR           | $\lor$   | `\|`                    | `x \| y`  | Sets each bit to 1 if one of the bits is 1.                                                |
| Bitwise XOR          | $\oplus$ | `^`                     | `x ^ y`   | Sets each bit to 1 if only one of the bits is 1.                                           |
| Left Shift           |          | `<<`                    | `x << n`  | Shifts the bits of x to the left by n places.                                              |
| Right Shift          |          | `>>`                    | `x >> n`  | Shifts the bits of x to the right by n places.                                             |
| Unsigned Right Shift |          | `>>>`                   | `x >>> n` | Shifts the bits of x to the right by n places (zero fill). Not available in all languages. |
{ #bitwise-ops}


Note: The "Unsigned Right Shift" operator (`>>>`) is not available in all programming languages and is typically used in languages that have distinct types for signed and unsigned integers. In C#, the right shift operator (`>>`) will maintain the sign bit (sign extension) for signed integers, while for unsigned integers, it will perform a zero-fill right shift.

https://en.wikipedia.org/wiki/Bitwise_operation