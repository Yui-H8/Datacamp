# Introduction to Polars
---
### Load a CSV into a DataFrame
* Load the "electric_vehicles.csv" into a Polars DataFrame called ev_df.
* Print the first three rows of the DataFrame using an appropriate method.
```python
# Load the CSV into a DataFrame
ev_df = pl.read_csv("electric_vehicles.csv")

# Print the first three rows
print(ev_df.head(3))
```
