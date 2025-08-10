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
```r
counties_selected <- counties %>%
  select(state, county, population)

counties_selected %>%
  # Filter for counties with a population above 1000000
  filter(population > 1000000, 
  state == 'California' )
```
### Filtering and arranging
* Filter for counties in the state of Texas that have more than ten thousand people (10000), and sort them in descending order of the percentage of people employed in private work.
```r
counties_selected <- counties %>%
  select(state, county, population, private_work, public_work, self_employed)

# Filter for Texas and more than 10000 people; sort in descending order of private_work
counties_selected %>%
  # Filter for Texas and more than 10000 people
  filter(state == 'Texas', population > 10000) %>%
  # Sort in descending order of private_work
  arrange(desc(private_work))
```
