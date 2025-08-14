# Case Studies: Network Analysis in R
---
### Finding Dyads and Triads
* Do a dyad census using the dyad_census() function.
* Do a triad census using the triad_census() function.
* Find the edge density using the edge_density() function.
```r
# The graph, amzn_g, is available
amzn_g

# Perform dyad census
dyad_census(amzn_g)

# Perform triad census
triad_census(amzn_g)

# Find the edge density
edge_density(amzn_g)
```
### Clustering and Reciprocity
