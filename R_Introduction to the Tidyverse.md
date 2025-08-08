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
```r
library(gapminder)
library(dplyr)

# Filter for China in 2002
gapminder %>%
filter( year == 2002, country == 'China')
```
---
### Arranging observations by life expectancy
* Sort the gapminder dataset in ascending order of life expectancy (lifeExp).
* Sort the gapminder dataset in descending order of life expectancy.
```r
library(gapminder)
library(dplyr)

# Sort in ascending order of lifeExp
gapminder %>%
    arrange(lifeExp)

  
# Sort in descending order of lifeExp
gapminder %>%
    arrange(desc(lifeExp))
```
### Filtering and arranging
* Use filter() to extract observations from just the year 1957, then use arrange() to sort in descending order of population (pop).
```r
library(gapminder)
library(dplyr)

# Filter for the year 1957, then arrange in descending order of population
gapminder %>%
    filter(year == 1957) %>%
    arrange(desc(pop))
```
---
### Using mutate to change or create a column
* Use mutate() to change the existing lifeExp column, by multiplying it by 12: 12 * lifeExp.
* Use mutate() to add a new column, called lifeExpMonths, calculated as 12 * lifeExp.
```r
library(gapminder)
library(dplyr)

# Use mutate to change lifeExp to be in months
gapminder %>%
  mutate(lifeExp = lifeExp * 12)

# Use mutate to create a new column called lifeExpMonths
gapminder %>%
  mutate(lifeExpMonths = lifeExp * 12)
```
### Combining filter, mutate, and arrange
