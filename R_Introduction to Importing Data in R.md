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
### read.delim
* Import "hotdogs.txt" with read.delim(). Call the resulting data frame hotdogs. The variable names are not on the first line, so make sure to set the header argument appropriately.
* Call summary() on hotdogs. This will print out some summary statistics about all variables in the data frame.
```r
# Import "hotdogs.txt": hotdogs
hotdogs <- read.delim("hotdogs.txt", header = FALSE) 

# Summarize hotdogs
summary(hotdogs)
```
### Assigning column names
* Complete the read.delim() function call by assigning the column names to "type", "calories", and "sodium".
