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
```r
# Finish the read.delim() call
hotdogs <- read.delim("hotdogs.txt", header = FALSE, col.names = c("type", "calories", "sodium"))

# Print the first 6 rows of hotdogs
head(hotdogs)
```
### Column classes
* The hotdogs data frame has been loaded. Go ahead and display the structure of hotdogs.
* In the colClasses argument of the second read.delim() call, set the first, second, and third columns to 'character', 'NULL' and 'numeric'.
* Display the structure of hotdogs2 and look for the difference.
```r
# Previous call to import hotdogs.txt
hotdogs <- read.delim("hotdogs.txt", header = FALSE, col.names = c("type", "calories", "sodium"))

# Display structure of hotdogs
str(hotdogs)

# Edit the colClasses argument to import the data correctly: hotdogs2
hotdogs2 <- read.delim("hotdogs.txt", header = FALSE, 
                       col.names = c("type", "calories", "sodium"),
                       colClasses = c("character", "NULL", "numeric"))


# Display structure of hotdogs2
str(hotdogs2)
```
### read.table
* Finish the read.table() call to load the tab-delimited file found at path.
* Call head() on hotdogs; this will print the first 6 observations in the data frame.
