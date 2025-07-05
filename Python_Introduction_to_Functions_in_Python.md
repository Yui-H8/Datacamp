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
```python
# Define shout with the parameter, word
def shout(word):
    """Print a string with three exclamation marks"""
    # Concatenate the strings: shout_word
    shout_word = word + '!!!'

    # Print shout_word
    print(shout_word)

# Call shout with the string 'congratulations'
shout('congratulations')
```
### Functions that return single values
* In the function body, concatenate the string in word with '!!!' and assign to shout_word.
* Replace the print() statement with the appropriate return statement.
* Call the shout() function, passing to it the string, 'congratulations', and assigning the call to the variable, yell.
* To check if yell contains the value returned by shout(), print the value of yell.
```python
# Define shout with the parameter, word
def shout(word):
    """Return a string with three exclamation marks"""
    # Concatenate the strings: shout_word
    shout_word = word + '!!!'

    # Replace print with return
    return shout_word

# Pass 'congratulations' to shout: yell
yell = shout('congratulations')

# Print yell
print(yell)
```
Great work! Here it made sense to assign the output of shout('congratulations') to a variable yell because the function shout actually returns a value, it does not merely print one.
### Functions with multiple parameters
* Modify the function header such that it accepts two parameters, word1 and word2, in that order.
* Concatenate each of word1 and word2 with '!!!' and assign to shout1 and shout2, respectively.
* Concatenate shout1 and shout2 together, in that order, and assign to new_shout.
* Pass the strings 'congratulations' and 'you', in that order, to a call to shout(). Assign the return value to yell.
```python
# Define shout with parameters word1 and word2
def shout(word1, word2):
    """Concatenate strings with three exclamation marks"""
    # Concatenate word1 with '!!!': shout1
    shout1 = word1 + '!!!'
    
    # Concatenate word2 with '!!!': shout2
    shout2 = word2 + '!!!'
    
    # Concatenate shout1 with shout2: new_shout
    new_shout = shout1 + shout2

    # Return new_shout
    return new_shout

# Pass 'congratulations' and 'you' to shout(): yell
yell = shout('congratulations', 'you')

# Print yell
print(yell)
```
### A brief introduction to tuples
* Unpack nums to the variables num1, num2, and num3.
* Construct a new tuple, even_nums composed of the same elements in nums, but with the 1st element replaced with the value, 2.
