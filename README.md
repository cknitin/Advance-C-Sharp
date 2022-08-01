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
#### Anonymous methods are the methods without a name, just the body. To define an inline delegate we can use Anonymous methods , with anonymous method we do not need to create an external method which saves some time

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

# Func , predicate and Action
#### These are referred as generic delegates

# Func : 
### Func can take any type of input and can return any type of output, it can take up to 16 paramters

```
Func<double,double> area = x => x * x;
Func<int,double> area = x => 3.14 * x * x;
```

```
Func<int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int> funcMethod = (int a1, int a2, int a3, int a4, int a5, 
int a6, int a7, int a8, int a9, int a10, int a11, int a12, int a13, int a14, int a15, int a16) => {
    return a2 + a3;
};

int a17 = funcMethod(1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16);
Console.WriteLine(a17);

```

# Action :
#### Action can take any type of input but can return void output only, means it simply doesn't return anything , it just takes input and processes it as per the definition.

#### but does not return any value, it can take up to 16 paramters

```
Action<string> res = () => Console.WriteLine("Hello I am James");

```

```
Action<int, int,int, int, int, int, int, int, int, int, int, int, int, int, int, int> actionMethod = (int a1, int a2, int a3, int a4, int a5,
int a6, int a7, int a8, int a9, int a10, int a11, int a12, int a13, int a14, int a15, int a16) => {
    Console.WriteLine(a1 + a2);
};

actionMethod(1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16);
```

# Predicate : 
#### Predicate can take any type of input but it can only return bool output.

```
predicate<string> x => x.Length > 5;
predicate<int> x => x % 2 == 0;
```

```
Predicate<string> isUpper = delegate (string s) { return s.Equals(s.ToUpper()); };
bool result = isUpper("hello world!!");
Console.WriteLine(result);
```

<br/>

> # Partitioning Operators In Linq

# Take
#### Take() standard query operator simply returns the first n items from a collection.

```
string[] countries = {"India","Australia","Pakistan","Japan","Nepal","England","America","Afganistan","Sri Lanka"};
var TopFiveCountries= countries.Take(5);
```

# TakeWhile
#### TakeWhile() operator simply returns items from a collection until the specified condition becomes true , TakeWhile() operator accepts a Func generic delegate.

```
string[] countries = { "India", "Australia", "Pakistan", "Japan", "Nepal" };
var res = countries.TakeWhile(condition);

public static bool condition(string str)
{
    if (str.Length <= 5)
    {
         return true;
    }
    return false;
}
    
            
```
