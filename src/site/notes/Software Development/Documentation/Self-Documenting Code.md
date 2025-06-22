---
{"dg-publish":true,"permalink":"/software-development/documentation/self-documenting-code/","tags":["nooblet","beginner","unfinished"],"noteIcon":"1"}
---

>[!Tldr]
>1. Only write comments/documentation for code that is hard to understand
>2. Try not to write code that's hard to understand

**Self-documenting code is code that conveys its purpose and function to an informed reader, without the need for comments or additional documentation** (for the most part). The idea of self-documenting code is not to neglect documentation and commenting, but to reduce the amount needed for someone to understand what the code is doing, and why it is doing it.

Here is a good example from stackoverflow:

> [!cite] [What is self-documenting code and can it replace well documented code?](https://stackoverflow.com/questions/209015/what-is-self-documenting-code-and-can-it-replace-well-documented-code)
> 
> [Timeline](https://stackoverflow.com/posts/209089/timeline)
> 
> Well, since this is about comments and code, let's look at some actual code. Compare this typical code:
> 
> ```java
> float a, b, c; a=9.81; b=5; c= .5*a*(b^2);
> ```
> 
> To this self-documenting code, which shows _what_ is being done:
> 
> ```java
> const float gravitationalForce = 9.81;
> float timeInSeconds = 5;
> float displacement = (1 / 2) * gravitationalForce * (timeInSeconds ^ 2);
> ```
> 
> And then to this documented code, which better explains _why_ it is being done:
> 
> ```java
> /* compute displacement with Newton's equation x = vₒt + ½at² */
> const float gravitationalForce = 9.81;
> float timeInSeconds = 5;
> float displacement = (1 / 2) * gravitationalForce * (timeInSeconds ^ 2);
> ```
> 
> And the final version of _code as documentation_ with zero comments needed:
> 
> ```java
> float computeDisplacement(float timeInSeconds) {
>     const float gravitationalForce = 9.81;
>     float displacement = (1 / 2) * gravitationalForce * (timeInSeconds ^ 2);
>     return displacement;
> }
> ```
> 
> Here's an example of a poor commenting style:
> 
> ```java
> const float a = 9.81; //gravitational force
> float b = 5; //time in seconds
> float c = (1/2)*a*(b^2) //multiply the time and gravity together to get displacement.
> ```
> 
> In the last example, comments are used when variables should have been descriptively named instead, and the results of an operation are summarized when we can clearly see what the operation is. I would prefer the self-documented second example to this any day, and perhaps that is what your friend is talking about when he says self-documented code.
> 
> I would say that it depends on the context of what you are doing. To me, the self-documented code is probably sufficient in this case, but a comment detailing the methodology behind what is behind done (in this example, the equation) is also useful.
> 
