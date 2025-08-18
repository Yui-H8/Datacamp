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
