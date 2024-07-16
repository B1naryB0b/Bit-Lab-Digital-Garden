---
{"dg-publish":true,"permalink":"/computer-science/maths/converting-maths-to-code/product-operator/","tags":["beginner","intermediate"]}
---

The product operator denoted with the mathematical symbol $\Pi$ is similar to the [[Computer Science/Maths/Converting Maths to Code/Summation Operator\|summation operator]], but instead of summing elements, it multiplies them. The general form of the product operator is:
$$
\begin{align}
&\prod_{i=0}^{n} x_{i} = x_{1} \times x_{2} \times x_{3} \times \dots \times x_{n} \\
&i = \text{index of product operator} \\
&n = \text{upper limit of product operator}
\end{align}
$$
# Translating to Code

In code, the product operator can be implemented using a `for` loop, where you multiply the elements in each iteration.

```csharp
float product = 1;
float[] x;
int n = x.Length;

for (int i = 0; i <= n; i++)
{
    product *= x[i];
}
```

Let's take a simple example:
$$
\begin{align}
P = \prod_{i=1}^{5} i = 1 \cdot 2 \cdot 3 \cdot 4 \cdot 5 &=  120\\
&=5!
\end{align}
$$

```csharp
float product = 1;
int n = 5;

for (int i = 1; i <= n; i++)
{
    product *= i;
}
```

Often, we need to compute the product of a function applied to a sequence of elements. For example:
$$
P = \prod_{i=0}^{n} f(x_{i}) = f(x_{0}) \cdot f(x_{1}) \cdot \dots \cdot f(x_{n})
$$

```csharp
float product = 1;
float[] x;
int n = x.Length;

for (int i = 0; i < n; i++)
{
    float hitDamage = x[i];
    
    product *= CalculateComboScore(hitDamage);
}

Console.WriteLine("Total Combo Score: " + product);
```

# Additional Resources

For more learning on the topic:
- [Multiplication (Product of a sequence) - Wikipedia](https://en.wikipedia.org/wiki/Multiplication#Product_of_a_sequence))
- [Mathmaine - Pi Notation (Product Notation)](https://mathmaine.com/2018/03/04/pi-notation/)
