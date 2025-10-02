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
<pre> 
shape: (3, 8)
┌────────────┬─────────────────┬───────────┬───────┬───────────┬───────┬─────────────┬───────┐
│ brand      ┆ model           ┆ style     ┆ accel ┆ top_speed ┆ range ┆ charge_rate ┆ price │
│ ---        ┆ ---             ┆ ---       ┆ ---   ┆ ---       ┆ ---   ┆ ---         ┆ ---   │
│ str        ┆ str             ┆ str       ┆ f64   ┆ f64       ┆ f64   ┆ f64         ┆ i64   │
╞════════════╪═════════════════╪═══════════╪═══════╪═══════════╪═══════╪═════════════╪═══════╡
│ SEAT       ┆ Mii Electric    ┆ Hatchback ┆ 12.3  ┆ 130.0     ┆ 195.0 ┆ 170.0       ┆ 20129 │
│ Smart      ┆ EQ fortwo coupe ┆ Hatchback ┆ 11.6  ┆ 130.0     ┆ 100.0 ┆ null        ┆ 21387 │
│ Volkswagen ┆ e-Up!           ┆ hatchback ┆ 11.9  ┆ 130.0     ┆ 195.0 ┆ 170.0       ┆ 21421 │
└────────────┴─────────────────┴───────────┴───────┴───────────┴───────┴─────────────┴───────┘
</pre>
### Inspect a DataFrame
Before diving into detailed analysis, you want to understand the structure and content of the EV dataset.
1. Print the number of rows and columns of the DataFrame ev_df.
```python
# Print number of rows and columns of ev_df
print(ev_df.shape)
```
2. Print the list of column names of the DataFrame ev_df.
```python
# Print the column names of ev_df
print(ev_df.columns)
```
3. Print the column names along with their dtypes.
```python
# Print the column names and dtypes
print(ev_df.schema)
```
4. Use a single method to get the shape, column names, dtypes and first rows in a vertical format.
