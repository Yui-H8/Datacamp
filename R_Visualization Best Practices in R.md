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
