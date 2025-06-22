---
{"dg-publish":true,"permalink":"/computer-science/object-oriented-programming/inheritance/","tags":["unfinished","beginner","intermediate"],"noteIcon":"1"}
---

Inheritance is when one [[Computer Science/Object Oriented Programming/Class\|class]] is derived from another [[Computer Science/Object Oriented Programming/Class\|class]], giving it access to the [[Computer Science/Programming/Methods\|methods]] and [[Computer Science/Variables/Variables\|variables]] of the base [[Computer Science/Object Oriented Programming/Class\|class]].

For instance you can have a [[Computer Science/Object Oriented Programming/Class\|class]] `Zombie` derive from a [[Computer Science/Object Oriented Programming/Class\|class]] `Enemy` which contains stats like `health`, `attackDamage` and `movementSpeed` it also contains a method called `TakeDamage()`.

This means that the `Zombie` [[Computer Science/Object Oriented Programming/Class\|class]] can use all of these [[Computer Science/Variables/Variables\|variables]] and [[Computer Science/Programming/Methods\|methods]], whilst also allowing you to write zombie specific functionality such as `EatBrains()` which plays a custom attack animation.

```csharp
private class Enemy
{
	public Player player;

	public int health = 5;
	public int attackDamage = 1;
	public float movementSpeed = 0.5f;

	public void TakeDamage(int damage)
	{
		health -= damage;
	}
}

//Can use all of the variables and methods in the Enemy class
private class Zombie : Enemy
{
	private void EatBrains()
	{
		DealDamage(player);
		//If close enough to player,
		//play animation
	}

	private void DealDamage(Player player)
	{
		player.TakeDamage(damage)
	}
}
```
