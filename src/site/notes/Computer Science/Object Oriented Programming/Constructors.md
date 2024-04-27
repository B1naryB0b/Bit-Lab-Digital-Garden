---
{"dg-publish":true,"permalink":"/computer-science/object-oriented-programming/constructors/","tags":["unfinished","beginner","intermediate"]}
---

This is code that is run when an [[Computer Science/Object Oriented Programming/Object\|object]] is created. It's generally used to initialise values and invoke any [[Computer Science/Programming/Methods\|methods]] that need to run for every new [[Computer Science/Object Oriented Programming/Object\|object]].

For instance if I wanted to construct a new `Card` in a card game and then load the values for that card afterwards I could write something like this:

```csharp
public class Card
{
	int manaCost;
	int attackPower;
	int health;
	
	public Card(CardStats stats)
	{
		manaCost = stats.cost;
		attackPower = stats.damage;
		health = stats.health;
	}

//Common card methods e.g. PlayCard, Attack, Taunt etc

}
```

```csharp
class DeckManager
{
	struct CardStats 
	{
		public int cost;
		public int damage;
		public int health;
	}
}
```
