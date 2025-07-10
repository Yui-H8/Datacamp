# Introduction to Python for Finance
---
### Run code vs. submit answer
### Python as a calculator
* Complete the following tasks by replacing ____ with the correct Python code:
   
Print the sum of 4 and 5.   
Print the result of subtracting 5 from 5.   
Print the result of multiplying 3 and 5.   
Print the result of dividing 10 by 2.   
```python
# Addition
print(4 + 5)

# Subtraction
print(5 - 5)

# Multiplication
print(3 * 5)

# Division
print(10 / 2)
```
### Creating numeric variables
* Assign 229.23 to the variable revenue_1.
* Assign 177.86 to the variable revenue_2.
* Assign 89.95 to the variable revenue_3.
```python
# Assign 229.23 to revenue_1
revenue_1 = 229.23

# Assign 177.86 to revenue_2
revenue_2 = 177.86

# Assign 89.95 to revenue_3
revenue_3 = 89.95
```
### Finding the average revenue
1. Create a new variable, total that represents the sum of revenue_1, revenue_2 and revenue_3.
```python
# Create the variable total and print the total revenue
total = revenue_1 + revenue_2 + revenue_3
print(total)
```
2. Find the average of total.
```python# Print the total revenue
total = revenue_1 + revenue_2 + revenue_3
print(total)

# Print the average revenue
average = total / 3
print(average)
```
### Creating different types of variables
1. Assign the string 'Apple' to the variable company_1.
```python
# Create company_1
company_1 = 'Apple'
print(company_1)
```
2. Assign the integer 2017 to the variable year_1.
```python
# Create year_1
year_1 = 2017
print(year_1)
```
3. Assign the float 229.23 to the variable revenue_1.
```python
# Create revenue_1
revenue_1 = 229.23
print(revenue_1)
```
### Determining types
* Print the data types associated with the variables company_1, year_1 and revenue_1.
```python
# Type of company_1
print(type(company_1))

# Type of year_1
print(type(year_1))

# Type of revenue_1
print(type(revenue_1))
```
### Combining data types
* Convert the data type of variables year_1, and revenue_1 to string.
* Use these new variables to create and print the following sentence: "The revenue of Apple in 2017 was $229.23 billion."
```python
# Update data types
year_1_str = str(year_1)
revenue_1_str = str(revenue_1)

# Create a complete sentence combining only the string data types
sentence = 'The revenue of ' + company_1 + ' in ' + year_1_str + ' was $' + revenue_1_str + ' billion.'

# Print sentence
print(sentence)
```
