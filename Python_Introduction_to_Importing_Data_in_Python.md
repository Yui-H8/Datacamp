# Introduction to Importing Data in Python
---
### Importing entire text files
* Open the file moby_dick.txt as read-only using a with statement and bind it to the variable file. Make sure to pass the filename enclosed in quotation marks ''.
* Print the contents of the file to the shell using the print() function. As Hugo showed in the video, you'll need to apply the method .read() to the object file and print the result.
```python
# Open a file as read-only and bind it to file
with open('moby_dick.txt', mode = 'r') as file:
  	# Print it
    print(file.read())
```
### Importing text files line by line
* Open moby_dick.txt using the with context manager and the variable file.
* Print the first three lines of the file to the shell by using .readline() three times within the context manager.
```python
# Read & print the first 3 lines
with open('moby_dick.txt') as file:
    print(file.readline())
    print(file.readline())
    print(file.readline())
```
### Why we like flat files and the Zen of Python
