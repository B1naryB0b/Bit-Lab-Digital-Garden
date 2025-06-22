---
{"dg-publish":true,"permalink":"/computer-science/object-oriented-programming/encapsulation/","tags":["unfinished","beginner"],"noteIcon":"1"}
---

Encapsulation is the practice of grouping [[Computer Science/Variables/Variables\|variables]] and [[Computer Science/Programming/Methods\|methods]] inside a [[Computer Science/Object Oriented Programming/Class\|class]] in a way that restricts direct access to some components of an [[Computer Science/Object Oriented Programming/Object\|object]]. It is used to prevent accidental interference and misuse of the [[Computer Science/Programming/Methods\|methods]] and data.

For example:
```csharp
public class PlayerWallet 
{
    private int coins;
	
    public PlayerWallet(int initialBalance)
    {
        coins = initialBalance;
    }
	
    public int GetBalance()
    {
        return coins;
    }
	
    public void Deposit(int amount)
    {
        if (amount > 0)
        {
            coins += amount;
        }
    }
	
	public bool Withdraw(int amount)
	{
		if (amount <= 0 || amount > coins)
		{
			return false;
		}
		
		coins -= amount;
		return true;
	}
}
```

In this case the value `coins` is encapsulated in a few different public [[Computer Science/Programming/Methods\|methods]] that modify the value. This allows for you to interact with it without risk of you performing an invalid operation.