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
```python
# Print the first values in a vertical format
print(ev_df.glimpse())
```
the .glimpse() method displays the first values in a vertical format that can be easier to read for DataFrames with many columns. In this case, it shows you the size of the dataset and a preview of the brands and performance characteristics.
---
### Creating a Series from a DataFrame
* Create a Series from the "brand" column of ev_df.
```python
# Create a Series from the brand column
print(ev_df["brand"])
```
*Correct, you can create a Series of the brand names by passing a single column name inside square brackets. The output of .select() is always a DataFrame.*
### Subsetting a DataFrame with bracket notation
1. Print the "brand", "model" and "price" columns (in that order) using bracket notation.
```python
# Extract the brand, model and price columns
print(ev_df[["brand", "model", "price"]])
```
<pre> output:
    shape: (106, 3)
    ┌────────────┬──────────────────────┬────────┐
    │ brand      ┆ model                ┆ price  │
    │ ---        ┆ ---                  ┆ ---    │
    │ str        ┆ str                  ┆ i64    │
    ╞════════════╪══════════════════════╪════════╡
    │ SEAT       ┆ Mii Electric         ┆ 20129  │
    │ Smart      ┆ EQ fortwo coupe      ┆ 21387  │
    │ Volkswagen ┆ e-Up!                ┆ 21421  │
    │ Smart      ┆ EQ forfour           ┆ 22030  │
    │ Skoda      ┆ CITIGOe iV           ┆ 24534  │
    │ …          ┆ …                    ┆ …      │
    │ Porsche    ┆ Taycan Turbo         ┆ 148301 │
    │ Lightyear  ┆ One                  ┆ 149000 │
    │ Porsche    ┆ Taycan Cross Turismo ┆ 150000 │
    │ Porsche    ┆ Taycan Turbo S       ┆ 180781 │
    │ Tesla      ┆ Roadster             ┆ 215000 │
    └────────────┴──────────────────────┴────────┘
</pre>
2. Print the last three rows of the "brand" and "price" columns (in that order) from ev_df using only bracket notation.
```python
# Print the last three rows of the brand and price columns
print(ev_df[-3:,["brand", "price"]])
```
<pre>
output:
    shape: (3, 2)
    ┌─────────┬────────┐
    │ brand   ┆ price  │
    │ ---     ┆ ---    │
    │ str     ┆ i64    │
    ╞═════════╪════════╡
    │ Porsche ┆ 150000 │
    │ Porsche ┆ 180781 │
    │ Tesla   ┆ 215000 │
    └─────────┴────────┘
</pre>
*Correct, with bracket notation you can combine row indexes and column names while using negative indexing from the end of the DataFrame.*
### Select a subset of columns with .select()
A fleet management client is particularly interested in how vehicle performance relates to price. You need to know if faster acceleration justifies higher prices across different models in ev_df.
1. Select the "model","accel","price" columns (in that order) using the .select() method.
```python
# Select the model, accel and price columns
print(ev_df.select("model", "accel", "price"))
```
