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
2. Complete the plotting code.
* Pass the graph to plot().
* Set the edge color to edge_color.
* Set the legend fill color to the unique values of edge_color.
```r
# From previous step
ip_df_from_to <- ip_df[c('from','to')]
ip_g <- graph_from_data_frame(ip_df_from_to, directed = TRUE)
edge_color <- ifelse(
  ip_df$salesrank.from <= ip_df$salesrank.to, "blue", "red"
)

plot(
  # Plot a graph of ip_g
  ip_g, 
  # Set the edge color
  edge.color = edge_color,
  edge.arrow.width = 1, edge.arrow.size = 0, edge.width = 4, 
  vertex.label = NA, vertex.size = 4, vertex.color = "black"
)
legend(
  "bottomleft", 
  # Set the edge color using edge_color
  fill = unique(edge_color), 
  legend = c("Lower to Higher Rank", "Higher to Lower Rank"), cex = 0.7
)
```
---
### Metrics through time
1.  Use lapply() to loop over the four graphs in time_graph, calculating the degree of each with mode "out".
* Use unlist() to flatten degree_count_list.
* Create a data frame with these columns.
* Set degree_count to degree_count_flat.
* Set vertex_name to the names of degree_count_flat.
* Set date to the dates, d, repeated using rep() as many times as the lengths() of degree_count_list.
```r
# Loop over time graphs calculating out degree
degree_count_list <- lapply(time_graph, degree, mode = "out")

# Flatten it
degree_count_flat <- unlist(degree_count_list)

degree_data <- data.frame(
  # Use the flattened counts
  degree_count = degree_count_flat,
  # Use the names of the flattened counts
  vertex_name = names(degree_count_flat),
  # Use the lengths of the count list
  date = rep(d, lengths(degree_count_list))
)
```
2. Three vertices are listed in important_vertices.
* Filter degree_data to keep rows where vertex_name is %in% important_vertices.
```r
# From previous step
degree_count_list <- lapply(time_graph, degree, mode = "out")
degree_count_flat <- unlist(degree_count_list)
degree_data <- data.frame(
  degree_count = degree_count_flat,
  vertex_name = names(degree_count_flat),
  date = rep(d, lengths(degree_count_list))
)

important_vertices <- c(1629, 132757, 117841)

important_degree_data <- degree_data %>% 
  # Filter for rows where vertex_name is
  # in the set of important vertices
  filter(vertex_name %in% important_vertices)
```
3. Using important_degree_data and ggplot(), plot degree_count versus date, colored by vertex_name.
* Add a path layer with geom_path().
```r
# From previous step
degree_count_list <- lapply(time_graph, degree, mode = "out")
degree_count_flat <- unlist(degree_count_list)
degree_data <- data.frame(
  degree_count = degree_count_flat,
  vertex_name = names(degree_count_flat),
  date = rep(d, lengths(degree_count_list))
)
important_vertices <- c(1629, 132757, 117841)
important_degree_data <- degree_data %>% 
  filter(vertex_name %in% important_vertices)

# Using important_degree_data, plot degree_count vs. date, colored by vertex_name 
ggplot(important_degree_data, aes(x = date, y = degree_count, color = vertex_name)) + 
  # Add a path layer
  geom_path()
```
### Plotting Metrics Over Time
1. Calculate the reciprocity by graph. This should take the same form as transitivity_by_graph except
* the metric should be "reciprocity" and the score function should be reciprocity().
```r
# Examine this code
transitivity_by_graph <- data.frame(
  date = d,
  metric = "transitivity",
  score = sapply(all_graphs, transitivity)
)

# Calculate reciprocity by graph
reciprocity_by_graph <- data.frame(
  date = d,
  metric = "reciprocity",
  score = sapply(all_graphs, reciprocity)
)
```
2. Use bind_rows() to bind the two data frames together (transitivity first).
```r
# From previous step
transitivity_by_graph <- data.frame(
  date = d,
  metric = "transitivity",
  score = sapply(all_graphs, transitivity)
)
reciprocity_by_graph <- data.frame(
  date = d,
  metric = "reciprocity",
  score = sapply(all_graphs, reciprocity)
)

# Bind these two datasets by row
metrics_by_graph <- bind_rows(transitivity_by_graph, reciprocity_by_graph)

# See the result
metrics_by_graph
```
3. Use ggplot() to visualize the graph metrics through time with a line using geom_path().
```r
# From previous steps
transitivity_by_graph <- data.frame(
  date = d,
  metric = "transitivity",
  score = sapply(all_graphs, transitivity)
)
reciprocity_by_graph <- data.frame(
  date = d,
  metric = "reciprocity",
  score = sapply(all_graphs, reciprocity)
)
metrics_by_graph <- bind_rows(transitivity_by_graph, reciprocity_by_graph)

# Using metrics_by_graph, plot score  vs. date, colored by metric
ggplot(metrics_by_graph, aes(x = date, y = score, color = metric)) +
  geom_path()
```
