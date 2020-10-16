---
title: "C# .NET: How to Convert DateTime to TimeSpan"
date: 2020-10-16T14:56:12+01:00
draft: true
categories:
- Basics
tags:
- DateTime
- TimeSpan
---

If you ever need to convert a `DateTime` or `DateTimeOffset` to a
`TimeSpan`, you can do it very simply using built-in operators
on the `DateTime` and `DateTimeOffset` types. If you subtract one
`DateTime` from another, the result will be a `TimeSpan` with the
difference between the two values.

<!--more-->

## Examples

Convert a `DateTimeOffset` to a `TimeSpan`:

```csharp
var dateTime1 = new DateTimeOffset(2020, 10, 16, 15, 1, 2, 345, TimeSpan.Zero);
var timeSpan1 = dateTime1 - DateTimeOffset.MinValue;

Console.WriteLine(timeSpan1);

// 737713.15:01:02.3450000

```

Convert a `DateTime` to a `TimeSpan`:

```csharp
var dateTime1 = new DateTime(2020, 10, 16, 15, 1, 2, 345);
var timeSpan1 = dateTime1 - DateTime.MinValue;

Console.WriteLine(timeSpan1);

// 737713.15:01:02.3450000
```

## Additional Notes

In general you should prefer the `DateTimeOffset` type to `DateTime`,
because it is able to handle times in specific timezones instead of just
"local" time and UTC (Universal Coordinated Time).

## Further Reading

Learn more about `DateTime` and `DateTimeOffset` operators from the
Microsoft Docs:

- [DateTimeOffset operators](https://docs.microsoft.com/en-us/dotnet/api/system.datetimeoffset?WT.mc_id=DOP-MVP-4032540#operators)
- [DateTime operators](https://docs.microsoft.com/en-us/dotnet/api/system.datetime?WT.mc_id=DOP-MVP-4032540#operators)

Learn more about the difference between `DateTime` and `DateTimeOffset`:

- [Choose between DateTime, DateTimeOffset, TimeSpan, and TimeZoneInfo](https://docs.microsoft.com/en-us/dotnet/standard/datetime/choosing-between-datetime?WT.mc_id=DOP-MVP-4032540)
