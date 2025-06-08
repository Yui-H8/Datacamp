## Introduction to Python for Developers
---
### Running your first Python script
* Click the Run Code button to execute the Python script and see the results in the Python shell area.
* Click the Submit Answer button to proceed to the next exercise.
```python
print("I Love Python")
```
---
### Writing your first Python script
* Use Python's built-in print() function to display "Learning Python".
```python
# Replace ____ below to display "Learning Python"
print("Learning Python")
```
### Python as a calculator
* Print the sum of 19 + 17.
* Print the result of subtracting 12 from 99.
```python
# Add 19 and 17
print(19 + 17)

# Subtract 12 from 99
print(99 - 12)
```
### More calculations
* Print the result of 9 multiplied by 2.
* Print the result of dividing 120 by 12.
```python
# Calculate and print 9 multiplied by 2
print(9 * 2)

# Print the result of dividing 120 by 12
print(120 / 12)
```
---
### Working with number variables
* Create a variable called account_balance with a value of 120.50.
* Print the account_balance variable.
```python
# Age of a customer
customer_age = 27

# Create account_balance variable
account_balance = 120.50

# Print account_balance
print(account_balance)
```
### Updating variable values
* Update the account_balance to be 1300000.00.
* Update the is_millionaire variable to be True.
* Print the is_millionaire variable to see its updated Boolean value.
```python
account_balance = 20000.00
is_millionaire = False

# Update account balance
account_balance = 1300000.00
# Update is_millionaire variable
is_millionaire = True

print(account_balance)
print(is_millionaire)
```
### Checking data types
1. Print the data type of the customer_age variable.
2. Print the data type of the variable account_balance.
```python
customer_age = 49
account_balance = 120078.89

# Print the data type of account_balance
print(type(account_balance))
```
3. Print the data type of the is_millionaire variable.
```pyyhon
customer_age = 49
account_balance = 120078.89
is_millionaire = False

# Print the data type of is_millionaire
print(type(is_millionaire))
```
---
### Multi-line strings
* Store the first review as a multi-line string variable called review_one.
* Store the second review as a multi-line string variable called review_two.
* Print review_one then print review_two.
```python
# Create review_one
review_one = """I really enjoy the courses,
and they are easy to fit into my busy schedule. 
I wish I had started using your platform sooner.
I'll be recommending you to my friends!!
"""

# Create review_two
review_two = """ One year ago, I was unsure of how to make progress in my career. 
Now, I work as a Prompt Engineer, and I can't thank you enough! 
Keep up the great work.
"""

# Print the two reviews individually
print(review_one)
print(review_two)
```
### Modifying string variables
* Update the variable so that "Intro" now reads "Introduction"
```python
most_popular_course = "Intro to Embeddings with the OpenAI API"

# Update the first word
most_popular_course = most_popular_course.replace("Intro", "Introduction")

print(most_popular_course)
```
* Swap spaces to underscores throughout the string contained in most_popular_course.
```python
# Swap spaces for underscores
most_popular_course = most_popular_course.replace(" ", "_")

print(most_popular_course)
```
* Update most_popular_course so that it only contains lowercase characters.
```Python
# Change to lowercase
most_popular_course = most_popular_course.lower()

print(most_popular_course)
```
---
### Building a party playlist
* Create a list variable called playlist, containing the following numeric and string values (in order):   
1, "Blinding Lights", 2, "One Dance", 3, "Uptown Funk".
* Print the list.
```python
# Create the playlist variable
playlist = [1, "Blinding Lights", 2, "One Dance", 3, "Uptown Funk"]

# Print the list
print(playlist)
```
