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
```python
# Unpack nums into num1, num2, and num3
num1, num2, num3 = nums

# Construct even_nums
even_nums = (2, num2, num3)
```
### Functions that return multiple values
* Modify the function header such that the function name is now shout_all, and it accepts two parameters, word1 and word2, in that order.
* Concatenate the string '!!!' to each of word1 and word2 and assign to shout1 and shout2, respectively.
* Construct a tuple shout_words, composed of shout1 and shout2.
* Call shout_all() with the strings 'congratulations' and 'you' and assign the result to yell1 and yell2 (remember, shout_all() returns 2 variables!).
```python
# Define shout_all with parameters word1 and word2
def shout_all(word1, word2):
    """Return a tuple of strings"""
    # Concatenate word1 with '!!!': shout1
    shout1 = word1 + '!!!'
    
    # Concatenate word2 with '!!!': shout2
    shout2 = word2 + '!!!'
    
    # Construct a tuple with shout1 and shout2: shout_words
    shout_words = (shout1, shout2)

    # Return shout_words
    return shout_words

# Pass 'congratulations' and 'you' to shout_all(): yell1, yell2
yell1, yell2 = shout_all('congratulations', 'you')

# Print yell1 and yell2
print(yell1)
print(yell2)
```
### Bringing it all together (1)
* Import the pandas package with the alias pd.
* Import the file 'tweets.csv' using the pandas function read_csv(). Assign the resulting DataFrame to df.
* Complete the for loop by iterating over col, the 'lang' column in the DataFrame df.
* Complete the bodies of the if-else statements in the for loop: if the key is in the dictionary langs_count, add 1 to the value corresponding to this key in the dictionary, else add the key to langs_count and set the corresponding value to 1. Use the loop variable entry in your code.
