# Dealing With Missing Data in R
---
### Using and finding missing values
* Create a vector, x, which has the values NA, NaN, Inf, ".", and "missing".
* Pass a vector x to any_na() and are_na() to find and explore which ones are missing.
```r
# Create x, a vector, with values NA, NaN, Inf, ".", and "missing"
x <- c(NA, NaN, Inf, ".", "missing")

# Use any_na() and are_na() on to explore the missings
any_na(x)
are_na(x)
```
### How many missing values are there?
Using the example dataframe of heights and weights dat_hw:
* Use n_miss() on the dataframe dat_hw to count the total number of missing values the dataframe.
* Use n_miss() on the variable dat_hw$weight to count the total number of missing values it.
* Similarly, use prop_miss(), n_complete(), and prop_complete() to get the proportion of missings, and the number and proportion of complete values for the dataframe and the variables.
