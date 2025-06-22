---
{"dg-publish":true,"permalink":"/computer-science/object-oriented-programming/class/","tags":["beginner","intermediate","unfinished"],"noteIcon":"1"}
---

```ad-info
Stole this amazing explanation from [iAmDev](https://www.youtube.com/@IAmDevtube/videos) on YouTube. I would highly recommend their channel for new devs, especially [this short playlist on OOP.](https://www.youtube.com/playlist?list=PLxvooGgpi4NeugSB4Pk546MXTPmGqPdc4)

<iframe width="100%" height="400" src="https://www.youtube.com/embed/K8eOkzQ_o9w?si=RZ1BDUVhUazYGn0H" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

A class is a blueprint/template of the [[Computer Science/Programming/Methods\|methods]] and [[Computer Science/Variables/Variables\|variables]] in a particular [[Computer Science/Object Oriented Programming/Object\|object]]. You can use it to create many [[Computer Science/Object Oriented Programming/Object\|objects]] that [[Computer Science/Object Oriented Programming/Inheritance\|inherit]] some of its properties.

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

By using the `Cannon` class above as a blueprint, we can now create a `Cannon` [[Computer Science/Object Oriented Programming/Object\|object]] for a small and scrappy pirate ship:

```csharp
class Scrappy 
{
	private Cannon mainCannon = new Cannon();
	mainCannon.damage = 10;
	mainCannon.Fire();
}
```

 And, by using a list, we can add a dozen cannons for a massive pirate flagship:

```csharp
class Flagship 
{
	private List<Cannon> cannons = new List<Cannon>();

	foreach(var cannon in cannons)
	{
		cannon.damage = 20;
		cannon.Fire();
	}
}
```

Because you use the cannon class, you don't need to reimplement `Fire()` or create a variable for `damage`, it's all contained within the `Cannon` class.