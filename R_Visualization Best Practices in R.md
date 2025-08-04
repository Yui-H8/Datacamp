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
