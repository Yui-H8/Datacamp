# Introduction to Data Visualization with ggplot2
---
### Drawing your first plot
* Load the ggplot2 package using library().
* Use str() to explore the structure of the mtcars dataset.
* ubmit the code. This will execute the example code. See if you can understand what ggplot does with the data.
```r
# Load the ggplot2 package
library(ggplot2)

# Explore the mtcars data frame with str()
str(mtcars)

# Execute the following command
ggplot(mtcars, aes(cyl, mpg)) +
  geom_point()
```
### Data columns types affect plot types
* Change the ggplot() command by wrapping factor() around cyl.
* Submit the code and see if the resulting plot is better this time.



Stellar scatterplotting! Notice that ggplot2 treats cyl as a factor.　　　

This time the x-axis does not contain variables like 5 or 7, only the values that are present in the dataset.
```r
# Load the ggplot2 package
library(ggplot2)

# Change the command below so that cyl is treated as factor
ggplot(mtcars, aes(x = factor(cyl), y = mpg)) +
  geom_point()
```
---
### Mapping data columns to aesthetics
1. Add a color aesthetic mapped to the displacement of the car engine: inside aes(), add a color argument equal to disp.
```r
# Edit to add a color aesthetic mapped to disp
ggplot(mtcars, aes(wt, mpg, color = disp)) +
  geom_point()
```
2. This time, map disp to the size aesthetic.
```r
# Change the color aesthetic to a size aesthetic
ggplot(mtcars, aes(wt, mpg, size = disp)) +
  geom_point()
```
### Understanding variables
### Adding geometries
