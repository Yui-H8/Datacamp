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
```python
# Select from 43rd character to the end of movie1
last_part = movie1[42:]
```
3. Select the substring going from the 33rd to the 42nd character of movie2. Assign it to the variable middle_part.
```python
# Select from 33rd to the 42nd character of movie2
middle_part = movie2[32:42]
```
4. Print the concatenation of the variables first_part, middle_part and last_part in that order. Print the variable movie2 and compare them.
```python
# Select the first 32 characters of movie1
first_part = movie1[:32]

# Select from 43rd character to the end of movie1
last_part = movie1[42:]

# Select from 33rd to the 42nd character
middle_part = movie2[32:42]

# Print concatenation and movie2 variable
print(first_part + middle_part + last_part) 
print(movie2)
```
### Palindromes
* Extract the substring from the 12th to the 30th character from the variable movie which corresponds to the movie title. Store it in the variable movie_title.
* Get the palindrome by reversing the string contained in movie_title.
* Complete the code to print out the movie_title if it is a palindrome.
```Python
# Get the word
movie_title = movie[11:30]

# Obtain the palindrome
palindrome = movie_title[::-1]

# Print the word if it's a palindrome
if movie_title == palindrome:
	print(movie_title)
```
---
### Normalizing reviews
1. Convert the string in the variable movie to lowercase. Print the result.
```python
# Convert to lowercase and print the result
movie_lower = movie.lower()
print(movie_lower)
```
2. Remove the $ that occur at the start and at the end of the string contained in movie_lower. Print the results.
```python
# Convert to lowercase and print the result
movie_lower = movie.lower()
print(movie_lower)

# Remove specified character and print the result
movie_no_sign = movie_lower.strip("$")
print(movie_no_sign)
```
3. Split the string contained in movie_no_sign into as many substrings as possible. Print the results.
```python
# Convert to lowercase and print the result
movie_lower = movie.lower()
print(movie_lower)

# Remove specified character and print the result
movie_no_sign = movie_lower.strip("$")
print(movie_no_sign)

# Split the string into substrings and print the result
movie_split = movie_no_sign.split()
print(movie_split)
```
4. To get the root of the second word contained in movie_split, select all the characters except the last one.
```python

```
