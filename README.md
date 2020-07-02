# QuaranTime

Just like [Unix time](https://en.wikipedia.org/wiki/Unix_time) is a system for 
describing a point in time relative to the Unix epoch, **QuaranTime** (from 
*quarantine time*) is also a way to represent time relative to the beginning 
of a [specific quarantine lockdown](https://en.wikipedia.org/wiki/COVID-19_pandemic_in_Argentina#Mandatory_lockdown).

[![Build Status](https://github.com/kzu/QuaranTime/workflows/build/badge.svg)](https://github.com/kzu/QuaranTime/actions)
[![Version](https://img.shields.io/nuget/vpre/QuaranTime.svg)](https://www.nuget.org/packages/QuaranTime)


## Why 

The Unix epoch, being 1 January 1970, happened a "long" time ago and therefore 
seconds (and even moreso milliseconds) from it are already fairly large numbers 
(currently, 10 and 13 digits respectively). By comparison, in Quarantine epoch 
they are 3 digits shorter currently. 

But moreover, since the COVID-19 epoch will likely be remembered far more vividly 
by current and future generations, it seems like a great opportunity to adopt a 
more easily relatable epoch.

The chosen date for the **QuaranTime** epoch is 3 March 2020 (2020-03-20) GMT-0300 
for a couple reasons: 
* It's very easy to remember (20/03/20) 
* I'm from Argentina ¯\_(ツ)_/¯

## How

Install the [package](https://nuget.org/packages/QuaranTime):

```
Install-Package QuaranTime
```

Use the provided extension methods:

```csharp
long seconds = DateTimeOffset.Now.ToQuaranTimeSeconds();
long milliseconds = DateTimeOffset.Now.ToQuaranTimeMilliseconds();
```

And to get the `DateTimeOffset`:

```csharp
DateTimeOffset fromSecs = QuaranTime.ToQuaranTimeSeconds(seconds);
DateTimeOffset fromMilliSecs = QuaranTime.FromQuaranTimeMilliseconds(milliseconds);
```

You can also directly access the constant `QuaranTime.Epoch` value.
