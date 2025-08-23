# Intermediate R for Finance
---
### What day is it?
* Type Sys.Date() to have R return the current date.
* Type Sys.time() to have R return the current date and time. Notice the difference in capitalization of Date vs time.
* Store Sys.Date() in the variable today.
* Use class() on today to confirm its class.
```r
# What is the current date?
Sys.Date()

# What is the current date and time?
Sys.time()

# Create the variable today
today <- Sys.Date()


# Confirm the class of today
class(today)
```
### From char to date
* Create a date variable named crash for "2008-09-29", the date of the largest stock market point drop in a single day.
Print crash.
* Use as.numeric() on crash to convert it to the number of days since January 1, 1970.
* Wrap as.numeric() around Sys.time() to see the current time in number of seconds since January 1, 1970.
* Attempt to create a date from "09/29/2008". What happens?
