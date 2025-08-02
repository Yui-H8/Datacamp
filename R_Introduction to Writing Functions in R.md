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
