# Introduction to Writing Functions in R
---
### Calling functions
1. The final line calculates the median number of gold medals each country won.
* Rewrite the call to median(), following best practices.
```r
# Look at the gold medals data
gold_medals

# Note the arguments to median()
args(median)

# Rewrite this function call, following best practices
median(gold_medals,na.rm = TRUE)
```
2. The final line calculates each country's ranking by number of gold medals. It uses negative gold_medals so that the country with the most medals will have 1st place: the largest positive value in gold_medals is the smallest ("most negative") value in -gold_medals.
* Rewrite the call to rank(), following best practices.
```r
# Note the arguments to rank()
args(rank)

# Rewrite this function call, following best practices
rank(-gold_medals,na.last = "keep", ties.method = "min")
```
### Your first function: tossing a coin
1. Simulate a single coin toss by using sample() to sample from coin_sides once.
```r
coin_sides <- c("head", "tail")

# Sample from coin_sides once
sample(coin_sides, size=1)
```
2. Write a template for your function, naming it toss_coin. The function should take no arguments. Don't include the body of the function yet.
