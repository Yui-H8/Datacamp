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
```r
library(gapminder)
library(dplyr)

# Filter the gapminder dataset for the year 1957
gapminder %>%
  filter(year == 1957)
```
### Filtering for one country and one year
* Filter the gapminder data to retrieve only the observation from China in the year 2002.
