---
{"dg-publish":true,"permalink":"/computer-science/object-oriented-programming/class/","tags":["beginner","intermediate","unfinished"]}
---

```ad-info
Stole this amazing explanation from [iAmDev](https://www.youtube.com/@IAmDevtube/videos) on YouTube. I would highly recommend their channel for new devs, especially [this short playlist on OOP.](https://www.youtube.com/playlist?list=PLxvooGgpi4NeugSB4Pk546MXTPmGqPdc4)
```

A class is a blueprint/template of the [[Computer Science/Object Oriented Programming/Methods\|methods]] and [[Computer Science/Variables/Variables\|variables]] in a particular [[Computer Science/Object Oriented Programming/Object\|object]]. You can use it to create many [[Computer Science/Object Oriented Programming/Object\|objects]] that [[Computer Science/Object Oriented Programming/Inheritance\|inherit]] some of its properties.

```ad-example
You are trying to build a pirate ship for a video game and need to create a bunch of cannons with similar functionality.
```
```csharp
class Cannon 
{
	public int damage;
	
	private void Fire()
	{
		CreateCannonBall(damage)
		ReloadAnimation();
	}
	
	private void CreateCannonBall()
	{
		//Generate a 3D ball and shoot it out, dealing damage
	}
	
	private void ReloadAnimation()
	{
		//Run reload animation
	}
}
```

By using a class as a blueprint we can now create a cannon for a small and scrappy pirate ship:

```csharp
class Scrappy 
{
	Cannon mainCannon = new Cannon();
	mainCannon.damage = 10;
	mainCannon.Fire();
}
```

 As well as for a massive pirate flagship:

```csharp
class Flagship 
{
	public List<Cannon> cannons = new List<Cannon>();

	foreach(var cannon in cannons)
	{
		cannon.damage = 20;
		cannon.Fire();
	}
}
```

Because you use the cannon class, you don't need to reimplement `Fire()` or create a variable for `damage`, it's all contained within the `Cannon` class.