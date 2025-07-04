# Introduction to Functions in Python
---
### Strings in Python
### Recapping built-in functions
Correct! It is important to remember that assigning a variable y2 to a function that prints a value but does not return a value will result in that variable y2 being of type NoneType.

### Write a simple function
* Complete the function header by adding the appropriate function name, shout.
* In the function body, concatenate the string, 'congratulations' with another string, '!!!'. Assign the result to shout_word.
* Print the value of shout_word.
* Call the shout function.
```python
# Define the function shout
def shout():
    """Print a string with three exclamation marks"""
    # Concatenate the strings: shout_word
    shout_word = ('congratulations' + '!!!')

    # Print shout_word
    print(shout_word)

# Call shout
shout()
```
### Single-parameter functions
* Complete the function header by adding the parameter name, word.
* Assign the result of concatenating word with '!!!' to shout_word.
* Print the value of shout_word.
* Call the shout() function, passing to it the string, 'congratulations'.
