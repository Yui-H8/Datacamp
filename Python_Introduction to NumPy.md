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
* Create another 3D array called new_game_and_solution with a different 2D game and 2D solution pair: new_sudoku_game and new_sudoku_solution. new_sudoku_game should appear before new_sudoku_solution.
* Create a 4D array called games_and_solutions by making an array out of the two 3D arrays: game_and_solution and new_game_and_solution, in that order.
* Print the shape of games_and_solutions.

```python
# Create a second 3D array of another game and its solution 
new_game_and_solution = np.array([new_sudoku_game, new_sudoku_solution])

# Create a 4D array of both game and solution 3D arrays
games_and_solutions = np.array([game_and_solution, new_game_and_solution])

# Print the shape of your 4D array
print(games_and_solutions.shape)
```
### Flattening and reshaping
1. Flatten sudoku_game so that it is a 1D array, and save it as flattened_game.   
Print the .shape of flattened_game.
```python
# Flatten sudoku_game
flattened_game = sudoku_game.flatten()

# Print the shape of flattened_game
print(flattened_game.shape)
```
2. Reshape the flattened_game back to its original shape of nine rows and nine columns; save the new array as reshaped_game.
```Python
# Flatten sudoku_game
flattened_game = sudoku_game.flatten()

# Print the shape of flattened_game
print(flattened_game.shape)

# Reshape flattened_game back to a nine by nine array
reshaped_game = flattened_game.reshape((9, 9))

# Print sudoku_game and reshaped_game
print(sudoku_game)
print(reshaped_game)
```
---
### The dtype argument
1. Using np.zeros(), create an array of zeros that has three rows and two columns; call it zero_array.   
Print the data type of zero_array.
```python
# Create an array of zeros with three rows and two columns
zero_array = np.zeros([3,2])

# Print the data type of zero_array
print(zero_array.dtype)
```
2. Create a new array of zeros called zero_int_array, which will also have three rows and two columns, but the data type should be np.int32.   
Print the data type of zero_int_array.
