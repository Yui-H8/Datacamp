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
