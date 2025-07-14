# Software Engineering Principles in Python
---
### Python modularity in the wild
* Complete the import statement to load the numpy package.
* Use numpy's array class to define arr.
* Use arr's sort method to sort the numpy array.
```python
# import the numpy package
import numpy as np

# create an array class object
arr = np.array([8, 6, 7, 5, 3, 0, 9])

# use the sort method
arr.sort()

# print the sorted array
print(arr)
```
### Leveraging documentation
1. View the documentation of the Counter.most_common method using the help() function.    
Note, you need to run the import statement before completing this step.
2. Correctly call Counter.most_common() by reading its documentation.   
Print the results stored in top_5_words.
```python
# Load the Counter function into our environment
from collections import Counter

# View the documentation for Counter.most_common
help(Counter.most_common)

# Use Counter to find the top 5 most common words
top_5_words = Counter(words).most_common(5)

# Display the top 5 most common words
print(top_5_words)
```
---
### Using pycodestyle
* Import the pycodestyle package.
* Create an instance of StyleGuide named style_checker.
* There are two files that we'll be checking; they're named 'nay_pep8.py' and 'yay_pep8.py'. Pass a list containing these file names to our style_checker's check_files method.
* print() the results of our style check to the console. Make sure to read the output!
```python
# Import needed package
import pycodestyle

# Create a StyleGuide instance
style_checker = pycodestyle.StyleGuide()

# Run PEP 8 check on multiple files
result = style_checker.check_files(['nay_pep8.py', 'yay_pep8.py'])

# Print result of PEP 8 style check
print(result.messages)
```
### Conforming to PEP 8
* Leverage the output of pycodestyle to edit the code to be compliant with PEP 8.
```python
# Assign data to x
x = [8, 3, 4]

# Print the data
print(x)
```
### PEP 8 in documentation
* Leverage the output of pycodestyle to edit the code's comments to be compliant with PEP 8.

my_script.py:2:15: E261 at least two spaces before inline comment   
my_script.py:5:16: E262 inline comment should start with '# '   
my_script.py:11:1: E265 block comment should start with '# '   
my_script.py:13:2: E114 indentation is not a multiple of four (comment)   
my_script.py:13:2: E116 unexpected indentation (comment)   
```python
def print_phrase(phrase, polite=True, shout=False):
    if polite:  # It's generally polite to say please
        phrase = 'Please ' + phrase

    if shout:  # All caps looks like a written shout
        phrase = phrase.upper() + '!!'

    print(phrase)


# Politely ask for help
print_phrase('help me', polite=True)
# Shout about a discovery
print_phrase('eureka', shout=True)
```

