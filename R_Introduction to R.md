# Introduction to R
---
### How it works
* In the editor there is already some sample code. Can you see which lines are actual R code and which are comments?
* Add a line of code that calculates the sum of 6 and 12, and submit your code.
```r
# Calculate 3 + 4
3 + 4

# Calculate 6 + 12
6 + 12
```
### Arithmetic with R
In its most basic form, R can be used as a simple calculator. Consider the following arithmetic operators:   

Addition: +   
Subtraction: -   
Multiplication: *   
Division: /   
Exponentiation: ^   
Modulo: %%   
The last two might need some explaining:

* Type 2^5 in the editor to calculate 2 to the power 5.
* Type 28 %% 6 to calculate 28 modulo 6.
* Submit the answer and have a look at the R output in the console.
* Note how the # symbol is used to add comments on the R code.
```r
# An addition
5 + 5 

# A subtraction
5 - 5 

# A multiplication
3 * 5

 # A division
(5 + 5) / 2 

# Exponentiation
2^5

# Modulo
28 %% 6
```
### Variable assignment
Over to you: complete the code in the editor such that it assigns the value 42 to the variable x in the editor. Submit the answer. Notice that when you ask R to print x, the value 42 appears.
```r
# Assign the value 42 to x
x <- 42

# Print out the value of the variable x
x
```
### Variable assignment (2)
* Type the following code in the editor: my_apples <- 5. This will assign the value 5 to my_apples.
* Type: my_apples below the second comment. This will print out the value of my_apples.
* Submit your answer, and look at the output: you see that the number 5 is printed. So R now links the variable my_apples to the value 5.
```r
# Assign the value 5 to the variable my_apples
my_apples <- 5

# Print out the value of the variable my_apples
my_apples
```
### Variable assignment (3)
* Assign to my_oranges the value 6.
* Add the variables my_apples and my_oranges and have R simply print the result.
* Assign the result of adding my_apples and my_oranges to a new variable my_fruit.
```r
# Assign a value to the variables my_apples and my_oranges
my_apples <- 5
my_oranges <- 6

# Add these two variables together
my_fruit = my_apples + my_oranges

# Create the variable my_fruit
my_fruit
```
### Apples and oranges
* Submit the answer and read the error message. Make sure to understand why this did not work.
* Adjust the code so that R knows you have 6 oranges and thus a fruit basket with 11 pieces of fruit.
```r
  # Assign a value to the variable my_apples
my_apples <- 5 

# Fix the assignment of my_oranges
my_oranges <- 6 

# Create the variable my_fruit and print it out
my_fruit <- my_apples + my_oranges 
my_fruit
```
### Basic data types in R
