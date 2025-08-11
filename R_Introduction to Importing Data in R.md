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
* Define the path to swimming_pools.csv, which is located in the "datasets" folder of the home directory.
```r
# Define the path
path <- file.path("~", "datasets", "swimming_pools.csv")

path
```
