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
