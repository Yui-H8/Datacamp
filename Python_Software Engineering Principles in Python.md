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
