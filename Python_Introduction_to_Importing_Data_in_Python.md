# Introduction to Importing Data in Python
---
### Importing entire text files
* Open the file moby_dick.txt as read-only using a with statement and bind it to the variable file. Make sure to pass the filename enclosed in quotation marks ''.
* Print the contents of the file to the shell using the print() function. As Hugo showed in the video, you'll need to apply the method .read() to the object file and print the result.
```python
# Open a file as read-only and bind it to file
with open('moby_dick.txt', mode = 'r') as file:
  	# Print it
    print(file.read())
```
### Importing text files line by line
* Open moby_dick.txt using the with context manager and the variable file.
* Print the first three lines of the file to the shell by using .readline() three times within the context manager.
```python
# Read & print the first 3 lines
with open('moby_dick.txt') as file:
    print(file.readline())
    print(file.readline())
    print(file.readline())
```
### Why we like flat files and the Zen of Python
In PythonLand, there are currently hundreds of Python Enhancement Proposals, commonly referred to as PEPs. PEP8, for example, is a standard style guide for Python, written by our sensei Guido van Rossum himself. 
### Using NumPy to import flat files
* Fill in the arguments of np.loadtxt() by passing file and a comma ',' for the delimiter.
* Fill in the argument of print() to print the type of the object digits. Use the function type().
* Execute the rest of the code to visualize one of the rows of the data.
```python
# Import packages
import numpy as np

# Assign filename to variable: file
file = 'digits.csv'

# Load file as array: digits
digits = np.loadtxt(file, delimiter=',')

# Print datatype of digits
print(type(digits))

# Select and reshape a row
im = digits[21, 1:]
im_sq = np.reshape(im, (28, 28))

# Plot reshaped data (matplotlib.pyplot already loaded as plt)
plt.imshow(im_sq, cmap='Greys', interpolation='nearest')
plt.show()
```
### Customizing your NumPy import
* Complete the arguments of np.loadtxt(): the file you're importing is tab-delimited, you want to skip the first row and you only want to import the first and third columns.
* Complete the argument of the print() call in order to print the entire array that you just imported.
```python
# Import numpy
import numpy as np

# Assign the filename: file
file = 'digits_header.txt'

# Load the data: data
data = np.loadtxt(file, delimiter='\t', skiprows=1, usecols=[0, 2])

# Print data
print(data)
```
### Importing different datatypes
* Complete the first call to np.loadtxt() by passing file as the first argument.
* Execute print(data[0]) to print the first element of data.
* Complete the second call to np.loadtxt(). The file you're importing is tab-delimited, the datatype is float, and you want to skip the first row.
* Print the 10th element of data_float by completing the print() command. Be guided by the previous print() call.
* Execute the rest of the code to visualize the data.

```python
# Assign filename: file
file = 'seaslug.txt'

# Import file: data
data = np.loadtxt(file, delimiter='\t', dtype=str)

# Print the first element of data
print(data[0])

# Import file as floats and skip the first row: data_float
data_float = np.loadtxt(file, delimiter='\t', dtype=float, skiprows=1)

# Print the 10th element of data_float
print(data_float[9])

# Plot a scatterplot of the data
plt.scatter(data_float[:, 0], data_float[:, 1])
plt.xlabel('time (min.)')
plt.ylabel('percentage of larvae')
plt.show()
```
---
### Using pandas to import flat files as DataFrames (1)
* Import the pandas package using the alias pd.
* Read titanic.csv into a DataFrame called df. The file name is already stored in the file object.
* In a print() call, view the head of the DataFrame.
```python
# Import pandas as pd
import pandas as pd

# Assign the filename: file
file = 'titanic.csv'

# Read the file into a DataFrame: df
df = pd.read_csv(file)

# View the head of the DataFrame
print(df.head())
```
### Using pandas to import flat files as DataFrames (2)
* Import the first 5 rows of the file into a DataFrame using the function pd.read_csv() and assign the result to data. You'll need to use the arguments nrows and header.
* Note that there is no header row in this file.
* Build a numpy array from the resulting DataFrame in data and assign to data_array.
* Execute print(type(data_array)) to print the datatype of data_array.
```python
# Assign the filename: file
file = 'digits.csv'

# Read the first 5 rows of the file into a DataFrame: data
data = pd.read_csv(file, nrows = 5, header = None)

# Build a numpy array from the DataFrame: data_array
data_array = data.to_numpy()

# Print the datatype of data_array to the shell
print(type(data_array))
```
### Customizing your pandas import
* Complete the arguments of pd.read_csv() to import titanic_corrupt.txt correctly using pandas:
* sep sets the delimiter to use, and works the same way as np.loadtxt()'s delimiter argument. Note that the file you're importing is tab-delimited.
* comment takes characters that comments occur after in the file, which in this case is '#'.
* na_values takes a list of strings to be treated as NA/NaN, in this case the string 'Nothing'.
* Execute the rest of the code to print the head of the resulting DataFrame and plot the histogram of the 'Age' of passengers aboard the Titanic.
