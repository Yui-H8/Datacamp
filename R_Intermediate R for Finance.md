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
```r
# Create crash
crash <- as.Date("2008-09-29")

# Print crash
crash

# crash as a numeric
as.numeric(crash)

# Current time as a numeric
as.numeric(Sys.time())

# Incorrect date format
as.Date("09/29/2008")
```
### Many dates
* Create another vector of dates containing the 4 days from "2017-02-05" to "2017-02-08" inclusive. Call this dates.
* Assign the days of the week "Sunday", "Monday", "Tuesday", "Wednesday", in that order, as names() of the vector dates.
* Subset dates using [ ] to retrieve only the date for "Monday".
```r
# Create dates from "2017-02-05" to "2017-02-08" inclusive
dates <- c("2017-02-05", "2017-02-06", "2017-02-07", "2017-02-08") 

# Add names to dates
names(dates) <- c("Sunday", "Monday", "Tuesday", "Wednesday")

# Subset dates to only return the date for Monday
dates["Monday"]
```
---
### Date formats (1)
In this exercise you will work with the date, "1930-08-30", Warren Buffett's birth date!
* Use as.Date() and an appropriate format to convert "08,30,1930" to a date (it is in the form of "month,day,year").
* Use as.Date() and an appropriate format to convert "Aug 30,1930" to a date.
* Use as.Date() and an appropriate format to convert "30aug1930" to a date.
```r
# "08,30,30"
as.Date("08,30,1930", format = "%m,%d,%Y")

# "Aug 30,1930"
as.Date("Aug 30,1930", format = "%M %d,%Y")

# "30aug1930"
as.Date("30aug1930", format = "%d%M%Y")
```
### Date formats (2)
* Create the vector dates from char_date, specifying the format so R reads them correctly.
* Modify dates using format() so that each date looks like "Jan 04, 17".
* Modify dates using format() so that each date looks like "01,04,2017".
```r
char_dates <- c("1jan17", "2jan17", "3jan17", "4jan17", "5jan17")

# Create dates using as.Date() and the correct format 
dates <- as.Date(char_dates, format = "%d%b%y")

# Use format() to go from "2017-01-04" -> "Jan 04, 17"
format(dates, format = "%b %d, %y")

# Use format() to go from "2017-01-04" -> "01,04,2017"
format(dates, format = "%m,%d,%Y")
```
### Subtraction of dates
