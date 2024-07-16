---
{"dg-publish":true,"permalink":"/computer-science/maths/converting-maths-to-code/summation-operator/","tags":["beginner","intermediate"]}
---

You may have seen the following mathematical symbol $\Sigma$ before, also known as the summation operator. For those familiar with the properties of the summation or [[Computer Science/Maths/Converting Maths to Code/Product Operator\|product operator]] you might be familiar with the general form of summation:
$$
\begin{align}
&\sum_{i=0}^{n} x_{i} = x_{1} + x_{2} + x_{3} + \dots + x_{n} \\
&i = \text{index of summation operator} \\
&n = \text{upper limit of summation operator}
\end{align}
$$
# Translating to Code

The summation operator is effectively just a `for` loop where you take the sum of the elements in each iteration.

```csharp
float sum = 0;
float[] x;
int n = x.Length;

for (int i=0, i<=n, i++)
{
	sum += x[i];
}
```

However, although this is useful, we don't get a simple case like this all the time. We need to be able to adapt this for different summations. Let's take a look at the example:
$$
S = \sum_{i=0}^{10} i = 0 + 1 + 2 + 3 + \dots + 10 = 55
$$
```csharp
float sum = 0;
int n = 10;

for (int i=0; i<=n; i++)
{
	sum += i;
}
```

We are also often looking at more complex and general cases than this where you need to take the sum of a function. For example:
$$
S = \sum_{i=0}^{n} f(x_{i}) = f(x_{1}) + f(x_{2}) + \dots + f(x_{n})
$$
```csharp
float sum = 0;
float[] x;
int n = x.Length;

for (int i=0; i<=n, i++)
{
	float sillyStiringFuel = x[i];
	
	sum += DispensedSillyString(sillyStiringFuel);
}

Console.WriteLine("Total Silly String Length: " + sum);
```

# Additional Resources

For more learning on the topic:
- [Summation - Wikipedia](https://en.wikipedia.org/wiki/Summation)
- [Khan Academy: Summation Notation](https://www.khanacademy.org/math/ap-calculus-ab/ab-integration-new/ab-6-3/a/review-summation-notation)
- [OpenDSA: Summations](https://opendsa-server.cs.vt.edu/ODSA/Books/CS3/html/Summations.html)