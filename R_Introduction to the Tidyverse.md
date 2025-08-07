# Introduction to the Tidyverse
---
### Loading the gapminder and dplyr packages
* Use the library() function to load the dplyr package, just like we've loaded the gapminder package for you.
* Type gapminder, on its own line, to look at the gapminder dataset.
```r
# Load the gapminder package
library(gapminder)

# Load the dplyr package
library(dplyr)

# Look at the gapminder dataset
gapminder
```
### Understanding a data frame
---
### Filtering for one year
* Add a filter() line after the pipe (%>%) to extract only the observations from the year 1957. Remember that you use == to compare two values.
