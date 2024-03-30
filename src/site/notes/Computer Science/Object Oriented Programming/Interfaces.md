---
{"dg-publish":true,"permalink":"/computer-science/object-oriented-programming/interfaces/","tags":["unfinished","intermediate"]}
---

Interfaces are contracts that tell you what a [[Computer Science/Object Oriented Programming/Class\|class]] does when you reference it.

A interface can be used to [[Computer Science/Object Oriented Programming/Decoupling\|decouple]] code that would otherwise require tight dependencies between your [[Computer Science/Object Oriented Programming/Class\|classes]]. It helps you make changes in one place without impacting other [[Computer Science/Object Oriented Programming/Class\|classes]].

For instance, I can have a bunch of different `Damage()` functions for a range of different objects with different properties.

```csharp
public class Gun
{
	//Other stuff in the class
	
	private void Shoot()
	{
		hitObject = SomeRayCastFunction();
		
		if (hitObject is RedBarrel redBarrel) 
		{ 
			redBarrel.TakeDamage(); 
		} 
		else if (hitObject is Door door) 
		{ 
			door.TakeDamage(); 
		} 
		else if (hitObject is Enemy enemy) 
		{ 
			enemy.TakeDamage(); 
		}
	}
}
```

However this doesn't scale very well and causes you to have increasingly more references with each damage interaction you add.

This is where interfaces come in. We define an interface as an [[Computer Science/Object Oriented Programming/Object\|object]] that has a `TakeDamage()` [[Computer Science/Programming/Methods\|function]].

```csharp
public interface IDamageable 
{
	public void TakeDamage();
}
```

Then we can have each [[Computer Science/Object Oriented Programming/Class\|class]] implement `TakeDamage()` separately and have then use the `IDamageable` interface.

```csharp
public class RedBarrel : IDamageable 
{
	//Other stuff in the class

	public void TakeDamage()
	{
		//Blow up barrel 
	}
}

public class Door : IDamageable 
{
	//Other stuff in the class

	public void TakeDamage()
	{
		//Shatter door mesh
	}
}

public class Enemy : IDamageable 
{
	//Other stuff in the class

	public void TakeDamage()
	{
		//Reduce HP
	}
}
```

We can now scale the script more easily. We can freely add more damage interactions without introducing dependencies between the `Gun` [[Computer Science/Object Oriented Programming/Class\|class]] and the damageable [[Computer Science/Object Oriented Programming/Class\|classes]].

```csharp
public class Gun
{
	//Other stuff in the class
	private void Shoot()
	{
		hitObject = SomeRayCastFunction();
		
		if (hitObject is IDamageable damageable) 
		{ 
			damageable.TakeDamage(); 
		}
	}
}

```