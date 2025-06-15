## Intermediate Python for Developers
---
### Get some assistance   
Not only does Python offer a range of built-in functions, but this even includes a way to find out more about data types, structures, and other functions.
1. Call the help() function on len.
```python
# Find out more about len()
print(help(len))

# Help on built-in function len in module builtins:
# len(obj, /)
#    Return the number of items in a container.
# None
```
2. Use help() on the int data type.
```Python
# Find out more about int
print(help(int))
```
Help on class type in module builtins:

class type(object)
 |  type(object_or_name, bases, dict)
 |  type(object) -> the object's type
 |  type(name, bases, dict) -> a new type
 |  
 |  Methods defined here:
 |  
 |  __call__(self, /, *args, **kwargs)
 |      Call self as a function.
 |  
 |  __delattr__(self, name, /)
 |      Implement delattr(self, name).
 |  
 |  __dir__(self, /)
 |      Specialized __dir__ implementation for types.
 |  
 |  __getattribute__(self, name, /)
 |      Return getattr(self, name).
 |  
 |  __init__(self, /, *args, **kwargs)
 |      Initialize self.  See help(type(self)) for accurate signature.
 |  
 |  __instancecheck__(self, instance, /)
 |      Check if an object is an instance.
 |  
 |  __repr__(self, /)
 |      Return repr(self).
 |  
 |  __setattr__(self, name, value, /)
 |      Implement setattr(self, name, value).
 |  
 |  __sizeof__(self, /)
 |      Return memory consumption of the type object.
 |  
 |  __subclasscheck__(self, subclass, /)
 |      Check if a class is a subclass.
 |  
 |  __subclasses__(self, /)
 |      Return a list of immediate subclasses.
 |  
 |  mro(self, /)
 |      Return a type's method resolution order.
 |  
 |  ----------------------------------------------------------------------
 |  Class methods defined here:
 |  
 |  __prepare__(...)
 |      __prepare__() -> dict
 |      used to create the namespace for the class statement
 |  
 |  ----------------------------------------------------------------------
 |  Static methods defined here:
 |  
 |  __new__(*args, **kwargs)
 |      Create and return a new object.  See help(type) for accurate signature.
 |  
 |  ----------------------------------------------------------------------
 |  Data descriptors defined here:
 |  
 |  __abstractmethods__
 |  
 |  __dict__
 |  
 |  __text_signature__
 |  
 |  ----------------------------------------------------------------------
 |  Data and other attributes defined here:
 |  
 |  __base__ = <class 'object'>
 |      The base class of the class hierarchy.
 |      
 |      When called, it accepts no arguments and returns a new featureless
 |      instance that has no instance attributes and cannot be given any.
 |  
 |  
 |  __bases__ = (<class 'object'>,)
 |  
 |  __basicsize__ = 880
 |  
 |  __dictoffset__ = 264
 |  
 |  __flags__ = 2148293632
 |  
 |  __itemsize__ = 40
 |  
 |  __mro__ = (<class 'type'>, <class 'object'>)
 |  
 |  __weakrefoffset__ = 368

 
3. Find out more about the list data structure, printing the results
```python
# Find out more about lists
print(help([]))
```
---
### Counting the elements
1. Use a function to count the number of key-value pairs in course_ratings, storing as a variable called num_courses, then print the variable.
```python
course_ratings = {"LLM Concepts": 4.7, 
                  "Introduction to Data Pipelines": 4.75, 
                  "AI Ethics": 4.62, 
                  "Introduction to dbt": 4.81}

# Print the number of key-value pairs
num_courses = len(course_ratings)
print(num_courses)
```
2. Use a function to count the number of courses in course_completions, storing as num_courses, and print this variable.
```python
course_completions = [97, 83, 121, 205, 56, 174, 92, 117, 164]

# Find the number of courses
num_courses = len(course_completions)
print(num_courses)
```

3. Use a function to count the number of characters in most_popular_course, storing as title_length, and print the variable.
```python
most_popular_course = "Introduction to dbt"

# How many characters are in most_popular_course?
title_length = len(most_popular_course)
print(title_length)
```
### Performing calculations
1. Add up and print the total number of course_completions.
```python
# Print the total number of course completions
print(sum(course_completions))
```
2. Print the largest value in course_completions.
```python
# Print the largest number of completions
print(max(course_completions))
```
3. Add up the values in course_completions and then divide this by the number of elements to get the average.
```python
# Print the average number of completions
print(sum(course_completions) / len(course_completions))
```
4. Round the average number of course completions to one decimal place.
```python
# Print the average number of completions, rounded to one decimal places
print(round(sum(course_completions) / len(course_completions), 1))
```
### Working with the string module
* Import the string module.
* Access the module's .ascii_lowercase attribute.
* Access the module's .punctuation attribute.
```python
# Import the string module
import string

# Print all ASCII lowercase characters
print(string.ascii_lowercase)

# Print all punctuation
print(string.punctuation)
```
### Importing from a module
* Import the date function from the datetime module.
* Create a variable called deadline, assigning a call of date(), passing in the numbers 2024, 1, and 19, in that order, separated by commas.
* Check the data type of deadline.
* Print the deadline variable.
```python
# Import date from the datetime module
from datetime import date

# Create a variable called deadline
deadline = date(2024, 1, 19)

# Check the data type
print(type(deadline))

# Print the deadline
print(deadline)
```
### Working with pandas
* Import the pandas module using an alias of pd.
* Create sales_df by using a pandas function to convert sales into a DataFrame.
* Preview the first five rows of sales_df.
```python
# Import pandas as pd
import pandas as pd

# Convert sales to a pandas DataFrame
sales_df = pd.DataFrame(sales)

# Preview the first five rows
print(sales_df.head())
```
### Performing calculations with pandas

