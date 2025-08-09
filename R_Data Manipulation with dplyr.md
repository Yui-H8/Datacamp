# Data Manipulation with dplyr
---
### Selecting columns
* Select the columns listed from the counties variable.
```r
counties %>%
  # Select the columns 
  select(state, county, population, poverty)
```
### Arranging observations
* Add a verb to sort the observations of the public_work variable in descending order.
```r
counties_selected <- counties %>%
  select(state, county, population, private_work, public_work, self_employed)

counties_selected %>%
  # Add a verb to sort in descending order of public_work
  arrange(desc(public_work))
```
### Filtering for conditions
1. Find only the counties that have a population above one million (1000000).
```r
counties_selected <- counties %>%
  select(state, county, population)

counties_selected %>%
  # Filter for counties with a population above 1000000
  filter(population > 1000000)
```
2. Find only the counties in the state of California that also have a population above one million (1000000).
