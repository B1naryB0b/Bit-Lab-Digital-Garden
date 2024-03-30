---
{"dg-publish":true,"permalink":"/computer-science/programming/methods/","tags":["#beginner","intermediate","unfinished"]}
---

A method is **some code that can be called/invoked from any point in a [[Computer Science/Object Oriented Programming/Class\|class]]** by using the name of the method. **A method is associated with a [[Computer Science/Object Oriented Programming/Class\|class]] and is what defines the behaviour of the [[Computer Science/Object Oriented Programming/Class\|class]]** and what actions an [[Computer Science/Object Oriented Programming/Object\|object]] created from the [[Computer Science/Object Oriented Programming/Class\|class]] can perform.

```ad-warning
Although the terms method and function are used interchangably they are slightly different in meaning. A method is a set of instructions that are *associated* with an [[Object|object]]/[[Class|class]], and a function is a set of instructions that *perform* a task. 

This means it is possible to write a function outside of a [[Class|class]]. So although **all methods are functions, not all functions are methods.**
```
```csharp
//GenerateProfileFunction is a function but not a method, it has no associated class
void GenerateProfileFunction(string firstNames, string lastName, int age)
{
	Console.Writeline("Full name: {firstNames} {lastName}")
	Console.Writeline("Age: {age}")
}

class Person 
{
	public string firstNames;
	public string lastName;
	public int age;
	
	//GenerateProfileMethod is a function as well as a method
	public void GenerateProfileMethod()
	{
		Console.Writeline("Full name: {firstNames} {lastName}")
		Console.Writeline("Age: {age}")
	}
}

Person person = new Person();

person.firstName = "Jeff";
person.lastName = "Bezos";
person.age = 59;

//Because it is a method we need to reference its associated object
person.GenerateProfileMethod();

Console.Writeline();

//Because it isn't a method we don't reference the associated object
GenerateProfileFunction(person.firstName, person.lastName, person.age);

```
```output
Full name: Jeff Bezos
Age: 59

Full name: Jeff Bezos
Age: 59
```
