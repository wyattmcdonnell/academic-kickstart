---
title: "Loading multiple RData objects without overwriting your existing objects"
date: 2019-12-27T12:29:15-06:00
draft: true
---
About 3 times a year, I forget how to load in multiple RData objects into a session. I always remember `load()` and I always get confused when an object in my environment changes and something breaks. This is because `load()` overwrites identically named objects. 

[Adam Lee Rich](https://adamleerich.com) has written about this already over at [R-bloggers](https://www.r-bloggers.com/safe-loading-of-rdata-files-2/). There's 1 particular function that's really helpful to [add to your .RProfile](https://www.r-bloggers.com/fun-with-rprofile-and-customizing-r-startup/):

```
loadEnvironment <- function(RData, env = new.env()){
    load(RData, env)
    return(env)
}
```

If you're like me and repeat object names (*e.g.* `df`, `db`, `fit`, `test`, *etc.*), you can avoid this by using `loadEnvironment()` and extract a particular object:

```
env.1 <- loadEnvironment('my.RData')
env.2 <- loadEnvironment('myOther.RData')
myFirstDF <- my.env$df
mySecondDF <- myOther.env$df
```
