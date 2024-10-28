Initially I wanted to solve this challenge with a `switch` block, like this:
```csharp
foreach (int ano in anosExperiencia)
{
    switch (ano)
    {
        case <= 3:
            classificacoes.Add("Junior");
            break;
        case <= 5:
            classificacoes.Add("Pleno");
            break;
        case > 5:
            classificacoes.Add("Senior");
            break;
    }
}
```
However, the test environment at the DIO probably use a C# version lower than 9.0, because that use raised exceptions:
![ErrorMessages](https://i.imgur.com/xd9A7pL.png)
So I needed to use an uglier `for` loop:
```csharp
foreach (int ano in anosExperiencia)
{
    if (ano <= 3)
    {
        classificacoes.Add("Junior");
    }
    else if (ano <= 5)
    {
        classificacoes.Add("Pleno");
    }
    else
    {
        classificacoes.Add("Senior");
    }
}
```
