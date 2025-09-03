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
