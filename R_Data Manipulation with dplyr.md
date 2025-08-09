# Data Manipulation with dplyr
---
### Selecting columns
* Select the columns listed from the counties variable.
```r
counties %>%
  # Select the columns 
  select(state, county, population, poverty)
```
