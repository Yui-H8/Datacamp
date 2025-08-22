# Introduction to R for Finance
---
### Your first R script
* An addition example has already been created for you.
* Add another line of code in the script to calculate the difference of 6 and 4.
* Note: Check out the # symbol in the script! This denotes a comment in your code. Comments are a great way to document your code, and are not run when you submit your answer.
```r
# Addition!
3 + 5

# Subtraction!
6 - 4
```
### Arithmetic in R (1)
* Some examples for addition, subtraction, and multiplication are shown for you.
* Type 4 / 2 in the script to perform division.
* Type 2^4 to raise 2 to the power of 4.
* Type 7 %% 3 to calculate 7 modulo 3.
* Don't forget to press Submit Answer when you finish!
```r
# Multiplication
3 * 4

# Division
4 / 2

# Exponentiation
2 ^ 4

# Modulo
7 %% 3
```
### Arithmetic in R (2)
### Assignment and variables (1)
* Assign a value of 200 to the savings variable in the script.
* Press Submit Answer and note how simply typing savings in the script asks R prints the value to the console!
```r
# Assign 200 to savings
savings <- 200

# Print the value of savings to the console
savings
```
### Assignment and variables (2)
my_money has been defined for you.
* Assign 200 to Dan's money.
* Follow the example in the exercise text and add your money to Dan's money.
* Add your money to Dan's money again, but this time save the result to our_money!
```r
# Assign 100 to my_money
my_money <- 100

# Assign 200 to dans_money
dans_money <- 200

# Add my_money and dans_money
my_money + dans_money

# Add my_money and dans_money again, save the result to our_money
our_money <- my_money + dans_money
```
### Financial returns (1)
Your new starting cash, January's return, and January's return multiplier have been defined for you.
* Use them to calculate post_jan_cash.
* Print post_jan_cash.
* What if the return for January was 10%? Calculate the new jan_mult_10.
* Calculate post_jan_cash_10 using the new multiplier!
* Print post_jan_cash_10 to see the impact of different interest rates!
```r
# Variables for starting_cash and 5% return during January
starting_cash <- 200
jan_ret <- 5
jan_mult <- 1 + (jan_ret / 100)

# How much money do you have at the end of January?
post_jan_cash <- starting_cash * jan_mult

# Print post_jan_cash
post_jan_cash

# January 10% return multiplier
jan_ret_10 <- 10
jan_mult_10 <- 1 + (jan_ret_10 / 100)

# How much money do you have at the end of January now?
post_jan_cash_10 <- starting_cash * jan_mult_10

# Print post_jan_cash_10
post_jan_cash_10
```
### Financial returns (2)
Your starting cash, and the returns for January and February have been given.
* Use them to calculate the January and February return multipliers: jan_mult and feb_mult.
* Use those multipliers and starting_cash to find your total_cash at the end of the two months.
* Print total_cash to see how your money has grown!
```r
# Starting cash and returns 
starting_cash <- 200
jan_ret <- 4
feb_ret <- 5

# Multipliers
jan_mult <- 1 + (jan_ret / 100)
feb_mult <- 1 + (feb_ret / 100)

# Total cash at the end of the two months
total_cash <- starting_cash * jan_mult * feb_mult

# Print total_cash
total_cash
```
