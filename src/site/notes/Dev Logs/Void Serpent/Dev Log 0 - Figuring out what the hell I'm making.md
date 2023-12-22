---
{"dg-publish":true,"permalink":"/dev-logs/void-serpent/dev-log-0-figuring-out-what-the-hell-i-m-making/","tags":["void-serpent"]}
---

# Welcome to the Void Serpent devlog!

I started this devlog waaaaay after I first started because at first this was just meant to be a portfolio piece (which I guess it technically still is) but slowly turned into an actual game project.

# The Start?

At this point I wasn't really planning on making the game I'm working on now, I just wanted to make a 2D spaceship shooter. Highly original, I know.

The first thing I wanted to nail down was movement. So I spent a few weeks just messing around with the movement system.

## Player Direction

I wanted to keep this simple, so the player just faced whichever direction the mouse was along the x-y plane (this is because I wanted to use a perspective camera for parallax).

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

Just call this in an `Update()` function in Unity and we were golden.
## Player Movement

### Inertial

I started out with an overcomplicated thrust system (because everyone knows complicated is better) which I called the inertial movement system due to how it glides forever and requires a significant force to change your direction. The movement was interesting but had some issues with gameplay.

#### Inertial Mark I

It worked by applying a force to the `Rigidbody2D` of the object depending on the thrust. You would use the `W/S` keys to increase and decrease the thrust which were clamped between `0` and `maxThrust`, and the velocity was similarly clamped.

```csharp
public void UpdateMovement(Rigidbody2D rb, Vector2 currentThrust)
{
    if (Input.GetKey(KeyCode.W))
    {
        currentThrust.y += thrustIncreaseRate * Time.fixedDeltaTime;
    }
    else if (Input.GetKey(KeyCode.S))
    {
        currentThrust.y -= thrustDecreaseRate * Time.fixedDeltaTime;
    }
    
    currentThrust.y = Mathf.Clamp(currentThrust.y, 0, maxThrust);
    
    rb.AddForce(transform.up * currentThrust.y);
    ClampVelocity(rb);
}

private void ClampVelocity(Rigidbody2D rb)
{
    if (rb.velocity.magnitude > terminalVelocity)
    {
        rb.velocity = rb.velocity.normalized * terminalVelocity;
    }
}
```

However, the direction that you shot in was the same as your thrust direction so it was a bit problematic, especially considering the thrust remained the same after changing directions, sort of like in a flight sim. 

![Inertial Thrust Mark I.excalidraw.png](/img/user/Excalidraw/Inertial%20Thrust%20Mark%20I.excalidraw.png)

This meant that you would have to look away from the enemy at maximum thrust, turn down the thrust to 0, only *then* could you turn around and shoot the enemy without moving towards them. Not ideal.

#### Inertial Mark II (Moonwalker)

So how did I fix this issue? I didn't, in fact I arguably made it a whole lot worse. But hey, nothing ventured, nothing gained.

The first thing I did was make it so you could set the thrust to negative values so you could glide backwards.

![67911b91af62338cfe3f782fb4ead0ff.gif](/img/user/_Bit%20Lab%20Organisation/Images/67911b91af62338cfe3f782fb4ead0ff.gif)

The key to moonwalking is to change the clamp for the thrust.

```csharp
currentThrust.y = Mathf.Clamp(currentThrust.y, -maxThrust, maxThrust);
```

And that is what a hard day of programming looks like.

Anyways, when I did this I could now shoot at the enemies whilst moving away from them. There was only one eenie weenie tiny winy problem. The controls were now inverted, you now moved away from your mouse instead of towards it which is mildly disorienting and felt trash to play but hey, maybe some tuning would fix it. 

It did not.

#### Inertial Mark III (I should have just made Kerbal at this point)

I made a rookie mistake (because I am one) and doubled down. I thought maybe the reason it feels bad is because when you switch from running to shooting behind you like something out of Die Hard, the thrust can sometimes land at some small negative number like `-0.1415` and kill some of your forward momentum.

![600px-DH3_Beretta-2.webp](/img/user/_Bit%20Lab%20Organisation/Images/600px-DH3_Beretta-2.webp)

So reworked a bunch of stuff and created a function to set thrust to 0 when you switch directions and add a small delay before you can go in the opposite direction. 

```csharp
public void UpdateMovement(Rigidbody2D rb, Vector2 currentThrust)
{
    currentThrust.y = AdjustThrust(currentThrust.y, KeyCode.W, KeyCode.S, canChangeVerticalDirection, Co_VerticalDirectionChangeDelay);
    
    rb.AddForce(transform.up * currentThrust.y);
    
    void ClampVelocity(Rigidbody2D rb)
    {
        rb.velocity = Vector2.ClampMagnitude(rb.velocity, terminalVelocity);
    }
    
    ClampVelocity(rb);
}

private float AdjustThrust(float current, KeyCode positiveKey, KeyCode negativeKey, bool canChangeDirection, Func<IEnumerator> delayMethod)
{
    if (Input.GetKey(positiveKey) && canChangeDirection)
    {
        if (current < 0 && !Mathf.Approximately(current, 0f))
        {
            current = DecreaseToZero(current, delayMethod);
        }
        else
        {
            current = Mathf.Clamp(current + thrustIncreaseRate * Time.fixedDeltaTime, 0, maxThrust);
        }
    }
}

private float DecreaseToZero(float current, Func<IEnumerator> delayMethod)
{
	current = Mathf.MoveTowards(current, 0, thrustDecreaseRate * Time.fixedDeltaTime);
	if (Mathf.Approximately(current, 0f))
	{
		StartCoroutine(delayMethod());
	}
	return current;
}

private IEnumerator Co_VerticalDirectionChangeDelay()
{
	canChangeVerticalDirection = false;
	yield return new WaitForSeconds(0.3f);
	canChangeVerticalDirection = true;
}
```

This *did feel better* but that was an extremely low bar. And so I felt confident that I just needed to double down once more (oh god please no). For the keen observer, you may have noticed that it writes `Co_VerticalDirectionChangeDelay`. That's only one orientation.

```csharp
public void UpdateMovement(Rigidbody2D rb, Vector2 currentThrust)
{
    currentThrust.y = AdjustThrust(currentThrust.y, KeyCode.W, KeyCode.S, canChangeVerticalDirection, Co_VerticalDirectionChangeDelay);
    
    currentThrust.x = AdjustThrust(currentThrust.x, KeyCode.D, KeyCode.A, canChangeHorizontalDirection, Co_HorizontalDirectionChangeDelay);
    
    rb.AddForce(transform.up * currentThrust.y + transform.right * currentThrust.x);
    
    void ClampVelocity(Rigidbody2D rb)
    {
        rb.velocity = Vector2.ClampMagnitude(rb.velocity, terminalVelocity);
    }
    
    ClampVelocity(rb);
}

private float AdjustThrust(float current, KeyCode positiveKey, KeyCode negativeKey, bool canChangeDirection, Func<IEnumerator> delayMethod)
{
    if (Input.GetKey(positiveKey) && canChangeDirection)
    {
        if (current < 0 && !Mathf.Approximately(current, 0f))
        {
            current = DecreaseToZero(current, delayMethod);
        }
        else
        {
            current = Mathf.Clamp(current + thrustIncreaseRate * Time.fixedDeltaTime, 0, maxThrust);
        }
    }
    else if (Input.GetKey(negativeKey) && canChangeDirection)
    {
        if (current > 0 && !Mathf.Approximately(current, 0f))
        {
            current = DecreaseToZero(current, delayMethod);
        }
        else
        {
            current = Mathf.Clamp(current - thrustIncreaseRate * Time.fixedDeltaTime, -maxThrust, 0);
        }
    }
    return current;
}

private float DecreaseToZero(float current, Func<IEnumerator> delayMethod)
{
    current = Mathf.MoveTowards(current, 0, thrustDecreaseRate * Time.fixedDeltaTime);
    if (Mathf.Approximately(current, 0f))
    {
        StartCoroutine(delayMethod());
    }
    return current;
}

private IEnumerator Co_VerticalDirectionChangeDelay()
{
    canChangeVerticalDirection = false;
    yield return new WaitForSeconds(0.3f);
    canChangeVerticalDirection = true;
}

private IEnumerator Co_HorizontalDirectionChangeDelay()
{
    canChangeHorizontalDirection = false;
    yield return new WaitForSeconds(0.3f);
    canChangeHorizontalDirection = true;
}
```

In the end I got this unholy abomination. I could now change the trust in 2 directions, this should be double the fun.

In the end, using this just gave me a headache, so I started from scratch. Maybe inertial wasn't the pick.

### Linear

