---
layout: post
title:  Advent of Code 2021 Day 6
draft: false
author: Daniel Wagner
date:   2021-12-06 17:36:00 +0100
category:
- software
tags:
- aoc
- software
- csharp
- dotnet
summary: Lanternfish solved using C# and Linq.
---
[![AoC 2021 Day 6](aoc-2021-06.webp)](https://adventofcode.com/2021/day/6)

The theme for today is:
> Sometimes looking up is better than searching

## Puzzle One

Think of clustering the lanternfish swarm into buckets of their current day of the creation cycle.

Use`GroupBy()` [^2] followed by `ToDictionary()` [^3] to compute the initial clustering:

```csharp
IDictionary<int, long> swarm = input.GroupBy(d => d).ToDictionary(i => i.Key, i => (long)i.Count());
```
Then you can computer the new clustering after an iteration by iterating over the buckets of your clustering and computing the new count of lanternfish and the new bucket(s).

## Puzzle Two

Puzzle two is only about performance. If your the implementation of puzzle one is efficient, it's just a change of parameters.

## Full Source

Full Source is available on GitHub. [^1]

[^1]: [https://github.com/danielwagn3r/AoC-2021/tree/main/Day6](https://github.com/danielwagn3r/AoC-2021/tree/main/Day6)
[^2]: [https://docs.microsoft.com/en-us/dotnet/api/system.linq.enumerable.groupby](https://docs.microsoft.com/en-us/dotnet/api/system.linq.enumerable.groupby)
[^3]: [https://docs.microsoft.com/en-us/dotnet/api/system.linq.enumerable.todictionary](https://docs.microsoft.com/en-us/dotnet/api/system.linq.enumerable.todictionary)
