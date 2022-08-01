# Advance C#

## What is a delegate?
#### It's a type in c#, which work like a function pointer, it can point to any method which has same signature, because its a type so it can be passed as paramter in method.

```
    
delegate void WhoAmIDel(string name);

void IamSuperHero(string name)
{
    Console.WriteLine($"I am {name}, I am Super Hero.");
}

 WhoAmIDel whoAmI1 = new WhoAmIDel(IamSuperHero);
 
 whoAmI1("James")

```

## Anonymous Method
#### Anonymous methods are the methods without a name, just the body.

```
Public delegate int Calculate(int x,int y);

calculate cal = delegate(int x,int y )
{
    return x+y;
} 

int result = cal(10,20);
```


## Lambda Expressions
#### Lambda expressions are shorthand way of defining inline delegates,
In order to define an inline delegate we can use Anonymous methods , with anonymous method we do not need to create an external method which saves some time.,Lambda expression takes this concept to one step further, and makes the delegate even more simpler as shown below.

```
Public delegate int Calculate(int x,int y);

Calculate c= (x,y) => x + y;

```

