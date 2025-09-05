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
* Have a look at the structure of the ilo_data set with str().
* After this, group the data by year using the group_by() function.
* Then, calculate the mean of both variables hourly_compensation and working_hours using the summarize() function.
```r
# Examine the structure of ilo_data
str(ilo_data)

# Group and summarize the data
ilo_data %>%
  group_by(year) %>%
  summarise(mean_hourly_compensation = mean(hourly_compensation),
            mean_working_hours = mean(working_hours))
```
### A basic scatter plot
* Filter the data for the year 2006. Save this filtered data set in a new variable called plot_data.
* Use plot_data to create a scatter plot with working_hours on the x-axis and hourly_compensation on the y-axis.
```r
# Filter for 2006
plot_data <- ilo_data %>%
  filter(year == 2006)
  
# Create the scatter plot
ggplot(plot_data) +
  geom_point(aes(x = working_hours, y = hourly_compensation))
```
### Add labels to the plot
* Use the labs() function to annotate your plot.
* Specify the correct arguments in the labs function call.
* Use ?labs to fire up the help function and see what arguments the labs() call takes.
* While it should be clear to what arguments most of the annotations should go, "The more people work, the less compensation they seem to receive" should be the title of the plot.
```r
# Create the plot
ggplot(plot_data) +
  geom_point(aes(x = working_hours, y = hourly_compensation)) +
  # Add labels
  labs(
    x = "Working hours per week",
    y = "Hourly compensation",
    title = "The more people work, the less compensation they seem to receive",
    subtitle = "Working hours and hourly compensation in European countries, 2006",
    caption = "Data source: ILO, 2017"
  )
```
---
### Apply a default theme
1. Assign your plot object into a variable called ilo_plot so you can save some typing later on.
```r
# Save your current plot into a variable: ilo_plot
ilo_plot <- ggplot(plot_data) +
  geom_point(aes(x = working_hours, y = hourly_compensation)) +
  labs(
    x = "Working hours per week",
    y = "Hourly compensation",
    title = "The more people work, the less compensation they seem to receive",
    subtitle = "Working hours and hourly compensation in European countries, 2006",
    caption = "Data source: ILO, 2017"
  )

# View it
ilo_plot
```
2. Try out the minimal theme on ilo_plot.
```r
# From previous step
ilo_plot <- ggplot(plot_data) +
  geom_point(aes(x = working_hours, y = hourly_compensation)) +
  labs(
    x = "Working hours per week",
    y = "Hourly compensation",
    title = "The more people work, the less compensation they seem to receive",
    subtitle = "Working hours and hourly compensation in European countries, 2006",
    caption = "Data source: ILO, 2017"
  )

# Add a minimal theme
ilo_plot +
  theme_minimal()
```
