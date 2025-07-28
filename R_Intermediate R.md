# Intermediate R
---
### Equality
* In the editor on the right, write R code to see if TRUE equals FALSE.
* Likewise, check if -6 * 14 is not equal to 17 - 101.
* Next up: comparison of character strings. Ask R whether the strings "useR" and "user" are equal.
* Finally, find out what happens if you compare logicals to numerics: are TRUE and 1 equal?
```r
# Comparison of logicals
TRUE == FALSE

# Comparison of numerics
-6 * 14 != 17 - 101

# Comparison of character strings
"useR" == "user"

# Compare a logical with a numeric
TRUE == 1
```
### Greater and less than
* Write R expressions to check whether:
    
-6 * 5 + 2 is greater than or equal to -10 + 1.    
"raining" is less than or equal to "raining dogs".   
TRUE is greater than FALSE.   
```r
# Comparison of numerics
-6 * 5 + 2 >= -10 + 1

# Comparison of character strings
"raining" <= "raining dogs"

# Comparison of logicals
TRUE > FALSE
```
### Compare vectors
Using relational operators, find a logical answer, i.e. TRUE or FALSE, for the following questions:
* On which days did the number of LinkedIn profile views exceed 15?
* When was your LinkedIn profile viewed only 5 times or fewer?
* When was your LinkedIn profile visited more often than your Facebook profile?
```r
# The linkedin and facebook vectors have already been created for you
linkedin <- c(16, 9, 13, 5, 2, 17, 14)
facebook <- c(17, 7, 5, 16, 8, 13, 14)

# Popular days
linkedin > 15

# Quiet days
linkedin <= 5

# LinkedIn more popular than Facebook
linkedin > facebook
```
### Compare matrices
Using the relational operators you've learned so far, try to discover the following:
* When were the views exactly equal to 13? Use the views matrix to return a logical matrix.
* For which days were the number of views less than or equal to 14? Again, have R return a logical matrix.
```r
# The social data has been created for you
linkedin <- c(16, 9, 13, 5, 2, 17, 14)
facebook <- c(17, 7, 5, 16, 8, 13, 14)
views <- matrix(c(linkedin, facebook), nrow = 2, byrow = TRUE)

# When does views equal 13?
views == 13

# When is views less than or equal to 14?
views <= 14
```
---
### Logical Operators
### & and |
Write R expressions to solve the following questions concerning the variable last:
* Is last under 5 or above 10?
* Is last between 15 and 20, excluding 15 but including 20?
