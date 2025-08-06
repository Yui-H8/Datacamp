# Visualization Best Practices in R
---
### Familiarizing with disease data
* Print data frame by simply calling the it: who_disease.
* Modify ggplot code so aes() contains the region as its x-axis mapping.
```r
# print data frame to inspect
who_disease

# set x aesthetic to region column
ggplot(who_disease, aes(region)) +
  geom_bar()
```
### Warming up data-wrangling
* Filter who_disease so we just only keep data from the 'AMR' region.
* Modify the aesthetics in the data to map the year to the x-axis, and cases to the y-axis.
* Lower the opacity (alpha) of the points to 0.5 to get a sense of overlap in geom_point()
```r
# filter data to AMR region. 
amr_region <- who_disease %>%
    filter(region == 'AMR')

# map x to year and y to cases. 
ggplot(amr_region, aes(x=year, y=cases)) + 
	# lower alpha to 0.5 to see overlap.   
  	geom_point(alpha = 0.5)
```
---
### The infamous P-I-E
* Add a column geometry (geom_col()) to the supplied ggplot object.
* Switch to polar coordinates by adding coord_polar().
```r
# Wrangle data into form we want. 
disease_counts <- who_disease %>%
	mutate(disease = ifelse(disease %in% c('measles', 'mumps'), disease, 'other')) %>%
	group_by(disease) %>%
	summarise(total_cases = sum(cases))

ggplot(disease_counts, aes(x = 1, y = total_cases, fill = disease)) +
	# Use a column geometry.
	geom_col() +
	# Change coordinate system to polar and set theta to 'y'.
	coord_polar(theta = 'y')
```
### Cleaning up the pie
* Add theme_void() to the ggplot object to clean up the background.
* Give the plot the title 'Proportion of diseases'.
```r
ggplot(disease_counts, aes(x = 1, y = total_cases, fill = disease)) +
	# Use a column geometry.
	geom_col() +
	# Change coordinate system to polar.
	coord_polar(theta = "y") +
	# Clean up the background with theme_void and give it a proper title with ggtitle.
	theme_void() +
	ggtitle('Proportion of diseases')
```
### How about a waffle?
* Give the case_counts vector names using the names() function.
* Call the waffle() function in the library waffle with the case_counts vector supplied as an argument.
```r
disease_counts <- who_disease %>%
	group_by(disease) %>%
	summarise(total_cases = sum(cases)) %>% 
	mutate(percent = round(total_cases/sum(total_cases)*100))

# Create an array of rounded percentages for diseases.
case_counts <- disease_counts$percent
# Name the percentage array
names(case_counts) <- disease_counts$disease

# Pass case_counts vector to the waffle function to plot
waffle(case_counts)
```
### Basic stacked bars
* Modify the aes() call to include the year mapped to the x-axis.
* Make bars fill the entire y-axis by adjusting position argument in geom_col().
```r
disease_counts <- who_disease %>%
	mutate(disease = ifelse(disease %in% c('measles', 'mumps'), disease, 'other')) %>%
	group_by(disease, year) %>% # note the addition of year to the grouping.
	summarise(total_cases = sum(cases))

# add the mapping of year to the x axis. 
ggplot(disease_counts, aes(x = year, y = total_cases, fill = disease)) +
	# Change the position argument to make bars full height
	geom_col(position = "fill")
```
### Ordering stack for readability
* Change the mutate function in the data-manipulation pipeline to turn disease into a factor with levels = c('measles', 'other', 'mumps').
* Re-plot using the same code as the last exercise.
```r
disease_counts <- who_disease %>%
	mutate(
		disease = factor(
			ifelse(disease %in% c('measles', 'mumps'), disease, 'other') ,
			levels = c('measles', 'other', 'mumps') ) # change factor levels to desired ordering
	) %>%
	group_by(disease, year) %>%
	summarise(total_cases = sum(cases)) 

# plot
ggplot(disease_counts, aes(x = year, y = total_cases, fill = disease)) +
	geom_col(position = 'fill')
```
