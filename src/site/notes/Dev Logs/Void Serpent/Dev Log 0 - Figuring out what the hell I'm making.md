---
{"dg-publish":true,"permalink":"/dev-logs/void-serpent/dev-log-0-figuring-out-what-the-hell-i-m-making/","tags":["void-serpent"]}
---

# Welcome to the Void Serpent devlog!

I started this devlog waaaaay after I first started because at first this was just meant to be a portfolio piece (which I guess it technically still is) but slowly turned into an actual game project.

# The Start?

At this point I wasn't really planning on making the game I'm working on now, I just wanted to make a tightly controlled twin-stick shooter set in space. Highly original, I know.

The first thing I wanted to nail down was movement. So I spent a few weeks just messing around with the movement system.

## Player Direction

I wanted to keep this simple, so the player just faced whichever direction the mouse was.

```csharp
private void RotateTowardsMouse()
{

	Ray ray = Camera.main.ScreenPointToRay(Input.mousePosition);

	float distanceToPlane;
	Plane playerPlane = new Plane(-Vector3.forward, transform.position);
	
	if (playerPlane.Raycast(ray, out distanceToPlane))
	{
		Vector3 pointOnPlane = ray.GetPoint(distanceToPlane);
		Vector3 direction = pointOnPlane - transform.position;

		direction.z = 0;

		float angle = Mathf.Atan2(direction.y, direction.x) * Mathf.Rad2Deg - 90f;
		
		Quaternion targetRotation = Quaternion.Euler(0, 0, angle);
		
		transform.rotation = Quaternion.RotateTowards(transform.rotation, targetRotation, rotationSpeed * Time.fixedDeltaTime);
	}
}
```

## Movement
### Inertial Mark I

I started out with a simple thrust system which I called the inertial movement system due to how it glides forever and requires a significant force to change your direction. The movement was interesting but had some issues with gameplay.

The direction that you shot in was the same as your thrust direction so it was a bit problematic 
![Inertial Thrust Mark I.excalidraw.png](/img/user/Excalidraw/Inertial%20Thrust%20Mark%20I.excalidraw.png)


