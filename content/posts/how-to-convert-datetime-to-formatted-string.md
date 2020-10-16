---
title: "C# .NET: How to Convert Date/Time to Formatted String"
date: 2020-10-16T15:43:58+01:00
draft: true
categories:
- Basics
tags:
- DateTime
- TimeSpan
- string
---

The .NET `DateTime`, `DateTimeOffset` and `TimeSpan` types provide good
support for formatting values as human-readable text. There are built-in,
pre-defined formats which will produce different outputs depending on the
current locale and culture info. You can also specify custom format
strings.

<!--more-->

To format a date/time value, just pass the format string to the value's
`ToString(format)` method.

## Examples

Format a `DateTimeOffset` to a full date and time string:

```csharp
var formatted = DateTimeOffset.Now.ToString("F");
Console.WriteLine(formatted);

// 16 October 2020 15:50:32
```

Format a `DateTimeOffset` to the ISO standard format:

```csharp
var formatted = DateTimeOffset.Now.ToString("O");
Console.WriteLine(formatted);

// 2020-10-16T15:51:16.5969257+01:00
```

Format a `DateTimeOffset` using a custom format string:

```csharp
var formatted = DateTimeOffset.Now.ToString("yyyy_MM_dd");
Console.WriteLine(formatted);

// 2020_10_16
```

Format a `TimeSpan` to the general short format:

```csharp
var formatted = DateTimeOffset.Now.TimeOfDay.ToString("g");
Console.WriteLine(formatted);

// 15:53:31.9297327
```

## Further reading

Learn more about Date/Time format strings from the Microsoft Docs:

- [Standard date and time format strings](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings?WT.mc_id=DOP-MVP-4032540)
- [Custom date and time format strings](https://docs.microsoft.com/en-us/dotnet/standard/base-types/custom-date-and-time-format-strings?WT.mc_id=DOP-MVP-4032540)
- [Standard TimeSpan format strings](https://docs.microsoft.com/en-us/dotnet/standard/base-types/standard-timespan-format-strings?WT.mc_id=DOP-MVP-4032540)
- [Custom TimeSpan format strings](https://docs.microsoft.com/en-us/dotnet/standard/base-types/custom-timespan-format-strings?WT.mc_id=DOP-MVP-4032540)