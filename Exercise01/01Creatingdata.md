## Creating a float
Before we start looking for Bayes' kidnapper, we need to fill out a Missing Puppy Report with details of the case. Each piece of information will be stored as a variable.  

* We define a variable using an equals sign (=). For instance, we would define the variable height:

```Python
# Fill in Bayes' age (4.0)
bayes_age = 4.0

# Display the variable bayes_age
print(bayes_age)
```

1. Define a variable called favorite_toy whose value is "Mr. Squeaky".
2. Define a variable called owner whose value is 'DataCamp'.
3. Show the values assigned to these variables.
```python
# Bayes' favorite toy
favorite_toy = "Mr.Squeaky"

# Bayes' owner
owner = 'DataCamp'

# Display variables
print(favorite_toy)
print(owner)
```
* Correct the mistakes in the code so that it runs without producing syntax errors.

```python
# One or more of the following lines contains an error
# Correct it so that it runs without producing syntax errors
birthday = '2017-07-14'
case_id = 'DATACAMP!123-456?'
```

* Use pd.read_csv() to load data from a CSV file called ransom.csv. This file represents the frequency of each letter in the ransom note for Bayes.

```python
# Import pandas
import pandas as pd

# Load the 'ransom.csv' into a DataFrame
r = pd.read_csv('ransom.csv')

# Display DataFrame
print(r)
```

