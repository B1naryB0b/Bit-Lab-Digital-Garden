---
{"dg-publish":true,"permalink":"/computer-science/object-oriented-programming/abstraction/","tags":["unfinished","intermediate"]}
---

```ad-tldr
Abstraction:
- Hides complexity from the user
- Reduces code repetition adn dependencies
- Allows for overriding implemention details 
- Partial abstaction with [[Computer Science/Object Oriented Programming/Abstract Classes\|abstract classes]]
- Total abstraction with [[Computer Science/Object Oriented Programming/Interfaces\|interfaces]] 
```

Abstraction is the process of hiding complexity from the user and showing only higher level actions they can take. For instance, you don't need to know how input handling works in detail, all you need to do is use abstractions. I can use methods like `Input.GetKey()` or `Input.OnMouseDown()`, that hide the implementation details but still allow me to manage inputs.

Abstraction can be achieved through the use of [[Abstract Classes|abstract classes]] and [[Computer Science/Object Oriented Programming/Interfaces\|interfaces]]. With [[Interfaces|interfaces]]  allowing for total abstraction, where you don't need to know any implementation details at all. In both of these you only need to define a [[Computer Science/Programming/Method Signature\|method signature]] and let each [[Computer Science/Object Oriented Programming/Class\|class]] implement the [[Computer Science/Programming/Methods\|method]] in their own way. 

```ad-warning
Abstractions can be used improperly, and in the worst cases they can [[Coupling|couple]] rather than [[Decoupling|decouple]] code. Abstractions should be based on real concepts in the system you are working on that allow you to describe it in natural language. When used correctly they [[Decoupling|decouple]] code and reduce [[Dependencies|dependencies]].

[Code Aesthetic: Abstraction can make your code worse](https://www.youtube.com/watch?v=rQlMtztiAoA)
```


https://raygun.com/blog/oop-concepts-java/#abstraction