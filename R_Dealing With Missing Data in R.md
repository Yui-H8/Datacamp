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
```r
# Use n_miss() to count the total number of missing values in dat_hw
n_miss(dat_hw)

# Use n_miss() on dat_hw$weight to count the total number of missing values
n_miss(dat_hw$weight)

# Use n_complete() on dat_hw to count the total number of complete values
n_complete(dat_hw)

# Use n_complete() on dat_hw$weight to count the total number of complete values
n_complete(dat_hw$weight)

# Use prop_miss() and prop_complete() on dat_hw to count the total number of missing values in each of the variables
prop_miss(dat_hw)
prop_complete(dat_hw)
```
### Working with missing values
### Summarizing missingness
1. Calculate summaries of missingness in the airquality dataset for variables using the miss_var_summary() function.
```r
# Summarize missingness in each variable of the `airquality` dataset
miss_var_summary(airquality)
```
2. Calculate summaries of missingness in the airquality dataset for the cases using the miss_case_summary() function.
```r
# Summarize missingness in each case of the `airquality` dataset
miss_case_summary(airquality)
```
3. Using the airquality dataset, use group_by() to create summaries for each variable and case, by each Month.
```r
# Return the summary of missingness in each variable, 
# grouped by Month, in the `airquality` dataset
airquality %>% group_by(Month) %>% 
miss_var_summary()

# Return the summary of missingness in each case, 
# grouped by Month, in the `airquality` dataset
airquality %>% group_by(Month) %>% miss_case_summary()
```
### Tabulating Missingness
For the airquality dataset:
* Tabulate missingness for each variable using miss_var_table().
* Tabulate missingness for every case using miss_case_table().
* Combine previous tabulations with dplyr's group_by() function to create tabulations for each variable and case, by each Month.
```r
# Tabulate missingness in each variable and case of the `airquality` dataset
miss_var_table(airquality)
miss_case_table(airquality)

# Tabulate the missingness in each variable, grouped by Month, in the `airquality` dataset
airquality %>% group_by(Month) %>% miss_var_table()

# Tabulate of missingness in each case, grouped by Month, in the `airquality` dataset
airquality %>% group_by(Month) %>% miss_case_table()
```
### Other summaries of missingness
Using the pedestrian dataset from naniar:
* Calculate summaries of missingness for the variables in datasets using miss_var_span(), for a span of 4000.
* Calculate summaries of missingness for the cases in datasets using miss_var_run().
* Combine with dplyr's group_by operator for month.
```r
# Calculate the summaries for each run of missingness for the variable, hourly_counts
miss_var_run(pedestrian, var = hourly_counts)

# Calculate the summaries for each span of missingness, 
# for a span of 4000, for the variable hourly_counts
miss_var_span(pedestrian, var = hourly_counts, span_every = 4000)

# For each `month` variable, calculate the run of missingness for hourly_counts
pedestrian %>% group_by(month) %>% miss_var_run(var = hourly_counts)

# For each `month` variable, calculate the span of missingness 
# of a span of 2000, for the variable hourly_counts
pedestrian %>% group_by(month) %>% miss_var_span(var = hourly_counts, span_every = 2000)
```
### Your first missing data visualizations
Using the riskfactors dataset from naniar:
* Use vis_miss() to visualize the missingness in the data.
* Use vis_miss() with cluster = TRUE to explore some clusters of missingness.
* Use vis_miss() and sort the missings with sort_miss to arrange the columns by missingness.
