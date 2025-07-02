# Python Toolbox
---
### Iterators vs. Iterables
### Iterating over iterables (1)
* Create a for loop to loop over flash and print the values in the list. Use person as the loop variable.
* Create an iterator for the list flash and assign the result to superhero.
* Print each of the items from superhero using next() 4 times.
```python
# Create a list of strings: flash
flash = ['jay garrick', 'barry allen', 'wally west', 'bart allen']

# Print each list item in flash using a for loop
for person in flash:
    print(person)

# Create an iterator for flash: superhero
superhero = iter(flash)

# Print each item from the iterator
print(next(superhero))
print(next(superhero))
print(next(superhero))
print(next(superhero))
```
### Iterating over iterables (2)
* Create an iterator object small_value over range(3) using the function iter().
* Using a for loop, iterate over range(3), printing the value for every iteration. Use num as the loop variable.
* Create an iterator object googol over range(10 ** 100).
```python
# Create an iterator for range(3): small_value
small_value = iter(range(3))

# Print the values in small_value
print(next(small_value))
print(next(small_value))
print(next(small_value))

# Loop over range(3) and print the values
for num in range(3):
    print(num)

# Create an iterator for range(10 ** 100): googol
googol = iter(range(10 ** 100))

# Print the first 5 values from googol
print(next(googol))
print(next(googol))
print(next(googol))
print(next(googol))
print(next(googol))

```
### Iterators as function arguments
* Create a range object that would produce the values from 10 to 20 using range(). Assign the result to values.
* Use the list() function to create a list of values from the range object values. Assign the result to values_list.
* Use the sum() function to get the sum of the values from 10 to 20 from the range object values. Assign the result to values_sum.
```python
# Create a range object: values
values = range(10, 21)

# Print the range object
print(values)

# Create a list of integers: values_list
values_list = list(values)

# Print values_list
print(values_list)

# Get the sum of values: values_sum
values_sum = sum(values)

# Print values_sum
print(values_sum)
```
