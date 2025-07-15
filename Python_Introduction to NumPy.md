# Introduction to NumPy
---
### Your first NumPy array
* Import NumPy using its generally accepted alias.
* Convert sudoku_list into a NumPy array called sudoku_array.
* Print the class type() of sudoku_array to check that your code has worked properly.
```python
# Import NumPy
import numpy as np

# Convert sudoku_list into an array
sudoku_array = np.array(sudoku_list)

# Print the type of sudoku_array 
print(type(sudoku_array))
```
### Creating arrays from scratch
1. Create and print an array filled with zeros called zero_array, which has two rows and four columns.
```python
# Create an array of zeros which has four columns and two rows
zero_array = np.zeros((2,4))
print(zero_array)
```
2. Create and print an array of random floats between 0 and 1 called random_array, which has three rows and six columns.
