# Intermediate Importing Data in Python
---
### Importing flat files from the web: your turn!
* Import the function urlretrieve from the subpackage urllib.request.
* Assign the URL of the file to the variable url.
* Use the function urlretrieve() to save the file locally as 'winequality-red.csv'.
* Execute the remaining code to load 'winequality-red.csv' in a pandas DataFrame and to print its head to the shell.

```python
# Import package
from urllib.request import urlretrieve

# Import pandas
import pandas as pd

# Assign url of file: url
url = 'https://assets.datacamp.com/production/course_1606/datasets/winequality-red.csv'

# Save file locally
urlretrieve(url, 'winequality-red.csv')

# Read file into a DataFrame and print its head
df = pd.read_csv('winequality-red.csv', sep=';')
print(df.head())
```
### Opening and reading flat files from the web
* Assign the URL of the file to the variable url.
* Read file into a DataFrame df using pd.read_csv(), recalling that the separator in the file is ';'.
* Print the head of the DataFrame df.
* Execute the rest of the code to plot histogram of the first feature in the DataFrame df.
```python
# Import packages
import matplotlib.pyplot as plt
import pandas as pd

# Assign url of file: url
url = 'https://assets.datacamp.com/production/course_1606/datasets/winequality-red.csv'

# Read file into a DataFrame: df
df = pd.read_csv(url, sep = ';')

# Print the head of the DataFrame
print(df.head())

# Plot first column of df
df.iloc[:, 0].hist()
plt.xlabel('fixed acidity (g(tartaric acid)/dm$^3$)')
plt.ylabel('count')
plt.show()
```
### Importing non-flat files from the web
* Assign the URL of the file to the variable url.
* Read the file in url into a dictionary xls using pd.read_excel() recalling that, in order to import all sheets you need to pass None to the argument sheet_name.
* Print the names of the sheets in the Excel spreadsheet; these will be the keys of the dictionary xls.
* Print the head of the first sheet using the sheet name, not the index of the sheet! The sheet name is '1700'
```python
# Import package
import pandas as pd

# Assign url of file: url
url = 'https://assets.datacamp.com/course/importing_data_into_r/latitude.xls'

# Read in all sheets of Excel file: xls
xls = pd.read_excel(url, sheet_name = None)

# Print the sheetnames to the shell
print(xls.keys())

# Print the head of the first sheet (using its name, NOT its index)
print(xls['1700'].head())
```
### Performing HTTP requests in Python using urllib
* Import the functions urlopen and Request from the subpackage urllib.request.
* Package the request to the url "https://campus.datacamp.com/courses/1606/4135?ex=2" using the function Request() and assign it to request.
* Send the request and catch the response in the variable response with the function urlopen().
* Run the rest of the code to see the datatype of response and to close the connection!
```python
# Import packages
from urllib.request import urlopen, Request

# Specify the url
url = "https://campus.datacamp.com/courses/1606/4135?ex=2"

# This packages the request: request
request = Request(url)

# Sends the request and catches the response: response
response = urlopen(request)

# Print the datatype of response
print(type(response))

# Be polite and close the response!
response.close()
```
### Printing HTTP request results in Python using urllib
* Send the request and catch the response in the variable response with the function urlopen(), as in the previous exercise.
* Extract the response using the read() method and store the result in the variable html.
* Print the string html.
* Hit submit to perform all of the above and to close the response: be tidy!
```python
# Import packages
from urllib.request import urlopen, Request

# Specify the url
url = "https://campus.datacamp.com/courses/1606/4135?ex=2"

# This packages the request
request = Request(url)

# Sends the request and catches the response: response
response = urlopen(request)

# Extract the response: html
html = response.read()

# Print the html
print(html)

# Be polite and close the response!
response.close()
```
### Performing HTTP requests in Python using requests
* Import the package requests.
* Assign the URL of interest to the variable url.
* Package the request to the URL, send the request and catch the response with a single function requests.get(), assigning the response to the variable r.
* Use the text attribute of the object r to return the HTML of the webpage as a string; store the result in a variable text.
* Hit submit to print the HTML of the webpage.
```python
# Import package
import requests

# Specify the url: url
url = "http://www.datacamp.com/teach/documentation"

# Packages the request, send the request and catch the response: r
r = requests.get(url)

# Extract the response: text
text = r.text

# Print the html
print(text)
```
### Parsing HTML with BeautifulSoup
* Import the function BeautifulSoup from the package bs4.
* Assign the URL of interest to the variable url.
* Package the request to the URL, send the request and catch the response with a single function requests.get(), assigning the response to the variable r.
* Use the text attribute of the object r to return the HTML of the webpage as a string; store the result in a variable html_doc.
* Create a BeautifulSoup object soup from the resulting HTML using the function BeautifulSoup().
* Use the method prettify() on soup and assign the result to pretty_soup.
* Hit submit to print to prettified HTML to your shell!
