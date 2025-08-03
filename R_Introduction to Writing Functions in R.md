# Introduction to Writing Functions in R
---
### Calling functions
1. The final line calculates the median number of gold medals each country won.
* Rewrite the call to median(), following best practices.
```r
# Look at the gold medals data
gold_medals

# Note the arguments to median()
args(median)

# Rewrite this function call, following best practices
median(gold_medals,na.rm = TRUE)
```
2. The final line calculates each country's ranking by number of gold medals. It uses negative gold_medals so that the country with the most medals will have 1st place: the largest positive value in gold_medals is the smallest ("most negative") value in -gold_medals.
* Rewrite the call to rank(), following best practices.
```r
# Note the arguments to rank()
args(rank)

# Rewrite this function call, following best practices
rank(-gold_medals,na.last = "keep", ties.method = "min")
```
### Your first function: tossing a coin
1. Simulate a single coin toss by using sample() to sample from coin_sides once.
```r
coin_sides <- c("head", "tail")

# Sample from coin_sides once
sample(coin_sides, size=1)
```
2. Write a template for your function, naming it toss_coin. The function should take no arguments. Don't include the body of the function yet.
```r
# Write a template for your function, toss_coin()
toss_coin <- function() {
  # (Leave the contents of the body for later)
# Add punctuation to finish the body
}
```
3. Copy your script, and paste it into the function body.
```r
# Your script, from a previous step
coin_sides <- c("head", "tail")
sample(coin_sides, 1)

# Paste your script into the function body
toss_coin <- function() {
  coin_sides <- c("head", "tail")
  sample(coin_sides, 1)
}
```
4. Call your function.
```r
# Your functions, from previous steps
toss_coin <- function() {
  coin_sides <- c("head", "tail")
  sample(coin_sides, 1)
}

# Call your function
toss_coin()
```
### Inputs to functions
1. Sample from coin_sides n_flips times with replacement
```r
coin_sides <- c("head", "tail")
n_flips <- 10

# Sample from coin_sides n_flips times with replacement
sample(coin_sides, n_flips, replace = TRUE)
```
* Update the definition of toss_coin() to accept a single argument, n_flips. The function should sample coin_sides n_flips times with replacement. Remember to change the signature and the body.
* Generate 10 coin flips.
```r
# Update the function to return n_flips coin tosses
toss_coin <- function(n_flips) {
  coin_sides <- c("head", "tail")
  sample(coin_sides, n_flips, replace = TRUE)
}

# Generate 10 coin tosses
toss_coin(10)
```
### Multiple inputs to functions
1. Bias the coin by weighting the sampling. Specify the prob argument so that heads are sampled with probability p_head (and tails are sampled with probability 1 - p_head).
```r
coin_sides <- c("head", "tail")
n_flips <- 10
p_head <- 0.8

# Define a vector of weights
weights <- c(p_head, 1 - p_head)

# Update so that heads are sampled with prob p_head
sample(coin_sides, n_flips, replace = TRUE, weights)
```
2. Update the definition of toss_coin() so it accepts an argument, p_head, and weights the samples using the code you wrote in the previous step.
* Generate 10 coin tosses with an 80% chance of each head.
