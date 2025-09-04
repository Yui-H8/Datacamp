# Communicating with Data in the Tidyverse
---
### Join the two data sets together
* Combine both ILO data frames ilo_hourly_compensation and ilo_working_hours using the inner_join() function of dplyr.
* Join both data frames by the variables "country" and "year".
```r
# Join both data frames
ilo_data <- ilo_hourly_compensation %>%
  inner_join(ilo_working_hours, by = c("country", "year"))

# Count the resulting rows
ilo_data  %>% 
    count()

# Examine ilo_data
ilo_data
```
### Change variable types
* Turn the variable year into a factor. Before turning it into a factor, turn it into a number using as.numeric(): call the as.numeric() function within the as.factor() function call.
* Turn the variable country into a factor.
```r
# Turn year and country into a factor
ilo_data_corrected <- ilo_data %>%
  mutate(
    year = as.factor(as.numeric(year)),  # 年を数値に変換した後、因子に変換
    country = as.factor(country)         # 国はそのまま因子に変換
  )


# See the results
ilo_data_corrected
```
### Filter the data for plotting
* Print european_countries to the console.
* Apply the filter() function to only retain countries which also appear in the european_countries vector. Use the %in% operator to retain only values that appear in the right-hand side of the operator.
```r
# Examine the European countries vector
european_countries

# Only retain European countries
ilo_data <- ilo_data %>%
  filter(country %in% european_countries)
```
### Some summary statistics
