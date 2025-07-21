# Regular Expressions in Python
---
### First day!
1. Find out how many characters the variable movie has.
```python
# Find characters in movie variable
length_string = len(movie)
print(length_string)
```
2. Convert the numeric variable length_string to a string representation.
```python
# Find characters in movie variable
length_string = len(movie)

# Convert to string
to_string = str(length_string)
```
3. Concatenate the predefined variable statement and the variable to_string adding a space between them. Print out the result.
```python
# Find characters in movie variable
length_string = len(movie)

# Convert to string
to_string = str(length_string)

# Predefined variable
statement = "Number of characters in this review:"

# Concatenate strings and print result
print(statement + " " + to_string)
```
### Artificial reviews
1. Select the first 32 characters of the variable movie1 and assign it to the variable first_part.
```python
# Select the first 32 characters of movie1
first_part = movie1[:32]
```
2. Select the substring going from the 43rd character to the end of movie1. Assign it to the variable last_part.
