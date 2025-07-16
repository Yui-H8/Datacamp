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
```python
# Create an array of random floats which has six columns and three rows
random_array = np.random.random((3,6))
print(random_array)
```
### A range array
* Using np.arange(), create a 1D array called one_to_ten which holds all integers from one to ten (inclusive).
* Create a scatterplot with doubling_array as the y values and one_to_ten as the x values.
```python
# Create an array of integers from one to ten
one_to_ten = np.arange(1,11)

# Create your scatterplot
plt.scatter(x = one_to_ten, y = doubling_array)
plt.show()
```
---
### 3D array creation
* Create a 3D array called game_and_solution by stacking the two 2D arrays, sudoku_game and sudoku_solution, on top of one another; in the final array, sudoku_game should appear before sudoku_solution.   
Print game_and_solution.
```python
# Create the game_and_solution 3D array
game_and_solution = np.array([sudoku_game, sudoku_solution])

# Print game_and_solution
print(game_and_solution)
```
### The fourth dimension


```python
# Create a second 3D array of another game and its solution 
new_game_and_solution = np.array([new_sudoku_game, new_sudoku_solution])

# Create a 4D array of both game and solution 3D arrays
games_and_solutions = np.array([game_and_solution, new_game_and_solution])

# Print the shape of your 4D array
print(games_and_solutions.shape)
```
