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
1. Explore the diamonds data frame with the str() function.
```r
# Explore the diamonds data frame with str()
str(diamonds)
```
2. Edit the plot code to add a point geom. Use the + operator to add geom_point() to the ggplot() command.
```r
# Add geom_point() with +
ggplot(diamonds, aes(carat, price)) +
  geom_point()
```
3. Add a smooth geom to the plot. Use the + operator to add geom_smooth().
```r
# Add geom_smooth() with +
ggplot(diamonds, aes(carat, price)) +
  geom_point() +
  geom_smooth()
```
### Changing one geom or every geom
1. Edit the plot code to map the color aesthetic to the clarity data variable.
```r
# Map the color aesthetic to clarity
ggplot(diamonds, aes(carat, price, color=clarity)) +
  geom_point() +
  geom_smooth()
```
2. Make the points translucent by setting the alpha argument to 0.4.
```r
# Make the points 40% opaque
ggplot(diamonds, aes(carat, price, color = clarity)) +
  geom_point(alpha=0.4) +
  geom_smooth()
```
### Saving plots as variables
1. Using the diamonds dataset, plot the price (y-axis) versus the carat (x-axis), assigning to plt_price_vs_carat.   
Using geom_point(), add a point layer to plt_price_vs_carat.
```r
# Draw a ggplot
plt_price_vs_carat <- ggplot(
  # Use the diamonds dataset
  diamonds,
  # For the aesthetics, map x to carat and y to price
  aes(carat, price)
) +　geom_point()

# Add a point layer to plt_price_vs_carat
plt_price_vs_carat
```
2. Add an alpha argument to the point layer to make the points 20% opaque, assigning to plt_price_vs_carat_transparent.     
Type the plot's variable name (plt_price_vs_carat_transparent) to display it.
```r
# From previous step
plt_price_vs_carat <- ggplot(diamonds, aes(carat, price))

# Edit this to make points 20% opaque: plt_price_vs_carat_transparent
plt_price_vs_carat_transparent <- plt_price_vs_carat + geom_point(alpha = 0.2)

# See the plot
plt_price_vs_carat_transparent
```
3. Inside geom_point(), call aes() and map color to clarity, assigning to plt_price_vs_carat_by_clarity.
* Type the plot's variable name (plt_price_vs_carat_by_clarity) to display it.
