### Data Manipulation with pandas
---
### Inspecting a DataFrame
* Print the head of the homelessness DataFrame.
```python
# Print the head of the homelessness data
print(homelessness.head())
```
* Print information about the column types and missing values in homelessness.
```python
# Print information about homelessness
print(homelessness.info())
```
* Print the number of rows and columns in homelessness.
```python
# Print the shape of homelessness
print(homelessness.shape)
```
* Print some summary statistics that describe the homelessness DataFrame.
```python
# Print a description of homelessness
print(homelessness.describe())
```
---
### Parts of a DataFrame
* Import pandas using the alias pd.
* Print a 2D NumPy array of the values in homelessness.
* Print the column names of homelessness.
* Print the index of homelessness.
```python
# Import pandas using the alias pd
import pandas as pd

# Print the values of homelessness
print(homelessness.values)

# Print the column index of homelessness
print(homelessness.columns)

# Print the row index of homelessness
print(homelessness.index)
```
