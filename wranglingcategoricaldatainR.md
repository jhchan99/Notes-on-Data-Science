# Problems with Categorical data

## Two ways to store categorical data

*Factors*
    - a variable used to categorize and store the data, having a limited number of different values, storing as a factor was better because factor variables only store factor labels ONCE
*Strings*
    - a character that is made of one character or contains a collection of characters, R now uses GLOBAL STRING POOL, so it is more effecient

_Example_

Male, Female. Non-Conforming

There are two different ways to store this information. One is with character *strings* and the other is as a *factor*.

## The Problem with factors

Storing data as factors instead of character strings has created some problems. Factors can be tricky to deal with because operations return different/unexpected values when applied to them

```r
{
    x1 <- c(10, 10, 20, 20, 40)

x1f <- factor(x1)

ds <- data.frame(x1, x1f)

library(dplyr)

ds <- ds %>% 
  mutate(x1recover = as.numeric(x1f))

}
```

x1recover should contain the same numeric values as x1, but instead will show that 10 has been mapped to 1, 20 was mapped to 2 and 40 was mapped to 3