# Advance C#

## What is a delegate?
### It's a type in c#, which work like a function pointer, it can point to any method which has same signature, because its a type so it can be passed as paramter in method.

<code>
    
`'delegate void WhoAmIDel(string name);

``void IamSuperHero(string name)
``{
``    Console.WriteLine($"I am {name}, I am Super Hero.");
``}

</code>

