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
```r
# The linkedin and last variable are already defined for you
linkedin <- c(16, 9, 13, 5, 2, 17, 14)
last <- tail(linkedin, 1)

# Is last under 5 or above 10?
last < 5 | last > 10

# Is last between 15 (exclusive) and 20 (inclusive)?
15 < last & last <= 20
```
### & and | (2)
* When did LinkedIn views exceed 10 and did Facebook views fail to reach 10 for a particular day? Use the linkedin and facebook vectors.
* When were one or both of your LinkedIn and Facebook profiles visited at least 12 times?
* When is the views matrix equal to a number between 11 and 14, excluding 11 and including 14?
```r
# The social data (linkedin, facebook, views) has been created for you
linkedin
facebook
views 
# linkedin exceeds 10 but facebook below 10
linkedin > 10 & facebook < 10

# When were one or both visited at least 12 times?
linkedin >= 12 | facebook >= 12

# When is views between 11 (exclusive) and 14 (inclusive)?
11 < views & views <= 14
```
### Blend it all together
* Select the entire second column, named day2, from the li_df data frame as a vector and assign it to second.
* Use second to create a logical vector, that contains TRUE if the corresponding number of views is strictly greater than 25 or strictly lower than 5 and FALSE otherwise. Store this logical vector as extremes.
* Use sum() on the extremes vector to calculate the number of TRUEs in extremes (i.e. to calculate the number of employees that are either very popular or very low-profile). Simply print this number to the console.
```r
# li_df is pre-loaded in your workspace
li_df
# Select the second column, named day2, from li_df: second
second <- li_df[,"day2"]
second
# Build a logical vector, TRUE if value in second is extreme: extremes
extremes <- (second > 25 | second < 5)

# Count the number of TRUEs in extremes
sum(extremes)
```
### The if statement
* Examine the if statement that prints out "Showing LinkedIn information" if the medium variable equals "LinkedIn".
* Code an if statement that prints "You are popular!" to the console if the num_views variable exceeds 15.
```r
# Variables related to your last day of recordings
medium <- "LinkedIn"
num_views <- 14

# Examine the if statement for medium
if (medium == "LinkedIn") {
  print("Showing LinkedIn information")
}

# Write the if statement for num_views
if (num_views > 15){
  print("You are popular!")
}
```
### Add an else
Add an else statement to both control structures, such that
* "Unknown medium" gets printed out to the console when the if-condition on medium does not hold.
* R prints out "Try to be more visible!" when the if-condition on num_views is not met.
```r
# Variables related to your last day of recordings
medium <- "LinkedIn"
num_views <- 14

# Control structure for medium
if (medium == "LinkedIn") {
  print("Showing LinkedIn information")
} else {
  print("Unknown medium")
}

# Control structure for num_views
if (num_views > 15) {
  print("You're popular!")
} else {
  print("Try to be more visible!")
}
```
### Customize further: else if
Add code to both control structures such that:
* R prints out "Showing Facebook information" if medium is equal to "Facebook". Remember that R is case sensitive!
* "Your number of views is average" is printed if num_views is between 15 (inclusive) and 10 (exclusive). Feel free to change the variables medium and num_views to see how the control structure respond. In both cases, the existing code should be extended in the else if statement. No existing code should be modified
```r
# Variables related to your last day of recordings
medium <- "LinkedIn"
num_views <- 14

# Control structure for medium
if (medium == "LinkedIn") {
  print("Showing LinkedIn information")
} else if (medium == "Facebook") {
  # Add code to print correct string when condition is TRUE
  print("Showing Facebook information")
} else {
  print("Unknown medium")
}

# Control structure for num_views
if (num_views > 15) {
  print("You're popular!")
} else if (num_views <= 15 & num_views > 10) {
  # Add code to print correct string when condition is TRUE
  print("Your number of views is average")
} else {
  print("Try to be more visible!")
}
```
### Else if 2.0
```r
if (number < 10) {
  if (number < 5) {
    result <- "extra small"
  } else {
    result <- "small"
  }
} else if (number < 100) {
  result <- "medium"
} else {
  result <- "large"
}
print(result)
```
