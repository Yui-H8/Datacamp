# Introduction to Importing Data in R
---
### read.csv
* Use read.csv() to import "swimming_pools.csv", which is located in the current directory, as a data frame with the name pools.
* Print the structure of pools using str().
```r
# Import swimming_pools.csv: pools
pools <- read.csv("swimming_pools.csv")

# Print the structure of pools
str(pools)
```
### Reading from a path
