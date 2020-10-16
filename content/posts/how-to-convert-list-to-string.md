---
title: "C# .NET: How to Convert List to String"
date: 2020-10-16T12:16:08+01:00
draft: false
categories:
- string
tags:
- strings
- lists
- arrays
---

.NET has a built-in method, `string.Join`, to create strings from lists,
arrays, or any type that implements `IEnumerable<string>`, and from
`object[]` arrays.

<!--more-->

## Examples

Join with a `string` separator:

```csharp
var fruits = new string[] { "Apples", "Bananas", "Cherries" };

var fruitStr = string.Join(", ", fruits);

Console.WriteLine(fruitStr);

// Apples, Bananas, Cherries
```

Join with a `char` separator (.NET Core & 5.0 only)

```csharp
var frameworks = new List<string>
{
    "netstandard2.0",
    "netcoreapp3.1",
    "net5.0"
};

var frameworkStr = string.Join(';', frameworks);

Console.WriteLine(frameworkStr);

// netstandard2.0;netcoreapp3.1;net5.0
```

Join an `object[]` array. This will call `.ToString()` on each object
in the array:

```csharp
var numbers = new object[] { 1, 2, 3 };

var numberStr = string.Join(", ", numbers);

Console.WriteLine(numberStr);

// 1, 2, 3
```

[Learn more about `string.Join` from the Microsoft Docs.](https://docs.microsoft.com/dotnet/api/system.string.join?WT.mc_id=DOP-MVP-4032540)
