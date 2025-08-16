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
1. Calculate the reciprocity of amzn_g using reciprocity(), assigning to actual_recip.
* Calculate the order of the graph with gorder(), assigning to n_nodes.
* Calculate the edge density of the graph with edge_density(), assigning to edge_dens.
```r
# Calculate reciprocity
actual_recip <- reciprocity(amzn_g)

# Calculate the order
n_nodes <- gorder(amzn_g)

# Calculate the edge density
edge_dens <- edge_density(amzn_g)
```
2. Simulate the reciprocity. Inside the for loop, Call erdos.renyi.game() to generate a simulated graph. Pass it the order, the edge density, and set directed to TRUE.
* Calculate the reciprocity of the simulated graph.
```r
# From previous step
actual_recip <- reciprocity(amzn_g)
n_nodes <- gorder(amzn_g)
edge_dens <- edge_density(amzn_g)

# Run the simulation
simulated_recip <- rep(NA, 1000)
for(i in 1:1000) {
  # Generate an Erdos-Renyi simulated graph
  simulated_graph <- erdos.renyi.game(n_nodes, edge_dens, directed = TRUE)
  # Calculate the reciprocity of the simulated graph
  simulated_recip[i] <- reciprocity(simulated_graph)
}
```
3. Compare the simulated reciprocity to the value from the original graph.
* Take a look at the original reciprocity, actual_recip.
* Calculate the 0.025, 0.5, and 0.975 quantiles of simulated_recip.
```r
# From previous steps
actual_recip <- reciprocity(amzn_g)

n_nodes <- gorder(amzn_g)
edge_dens <- edge_density(amzn_g)
simulated_recip <- rep(NA, 1000)
for(i in 1:1000) {
  simulated_graph <- erdos.renyi.game(n_nodes, edge_dens, directed = TRUE)
  simulated_recip[i] <- reciprocity(simulated_graph)
}

# Reciprocity of the original graph
actual_recip

# Calculate quantile of simulated reciprocity
quantile(simulated_recip , c(0.025, 0.5, 0.975))
```  
### Important Products
1. Use degree() to calculate the "out' degrees of amzn_g by setting the mode to "out".
* Calculate the "in" degrees in a similar manner.
* Use table() to see the distribution of vertex "out" degrees.
* Do the same for the "in" degrees.
```r
# Calculate the "out" degrees
out_degree <- degree(amzn_g, mode = "out")

## ... and "in" degrees
in_degree <- degree(amzn_g, mode = "in")

# See the distribution of out_degree
table(out_degree)

## ... and of in_degree
table(in_degree)
```
2. Define a logical vector of important cases: where out_degree is greater than 3 and in_degree is less than 3.
* Use V() to get the vertices of amzn_g, and use square brackets to filter on is_important to find the important products.
```r
# From previous step
out_degree <- degree(amzn_g, mode = "out")
in_degree <- degree(amzn_g, mode = "in")

# Create condition of out degree greater than 3
# and in degree less than 3
is_important <- out_degree > 3 & in_degree < 3

# Subset vertices by is_important
imp_prod <- V(amzn_g)[is_important]

# Output the vertices
print(imp_prod)
```
### What Makes an Important Product?
1. Select the from and to columns from ip_df, assigning to ip_df_from_to.
* Use graph_from_data_frame() to create a directed graph from ip_df_from_to.
* Define the edge color to be blue if ip_df$salesrank.from is less than or equal to ip_df$salesrank.to, and red otherwise.
```r
# Select the from and to columns from ip_df
ip_df_from_to <- ip_df[c("from", "to")]

# Create a directed graph from the data frame
ip_g <- graph_from_data_frame(ip_df_from_to, directed =TRUE)

# Set the edge color. If salesrank.from is less than or 
# equal to salesrank.to then blue else red.
edge_color <- ifelse(
  ip_df$salesrank.from <= ip_df$salesrank.to, 
  yes = "blue", 
  no = "red"
)
```
