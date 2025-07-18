# Introduction to Data Visualization with Plotly in Python
---
### Playing with a Plotly Figure
### Fixing a Plotly figure
* Define x_column and y_column using the "month" and "sales" columns.
* Set chart_title to "Sales for Jan-Mar 2025".
* Create a bar plot using these variables.
```python
# Define the x and y axis columns
x_column = "month"
y_column = "sales"

# Define the chart title
chart_title = "Sales for Jan-Mar 2025"

# Create a bar plot
fig = px.bar(
    data_frame=monthly_sales, x=x_column, y=y_column, title=chart_title)

fig.show()
```
---
### Student scores bar graph
* Examine the head of the student_scores DataFrame that has been printed for you.
* Create a bar plot, setting the y-axis to be the score and the x-axis to be the student name.
* Add a title to the plot: call it "Student Scores by Student".
```python
# Create the bar plot
fig = px.bar(data_frame=student_scores, 
             x="student_name", 
             y="score", 
             title="Student Scores by Student")

# Show the plot
fig.show()
```
### Box plot of company revenues
* Examine the head of the provided revenues DataFrame that has been printed for you.
* Create a box plot, setting the appropriate y-axis for company revenue data.
* Set the hover_data (a list of one string value) to show the company name.
```python
# Create the box plot
fig = px.box(
  			# Set the data
  			data_frame=revenues, 
  			# Set the y variable
            y="Revenue", 
            # Add in hover data to see outliers
            hover_data=["Company"])

# Show the plot
fig.show()
```
### Histogram of company revenues
* Create a histogram using px.histogram() and the appropriate DataFrame.
* Set the column Revenue to be used along the x-axis.
* Set the number of bins to 5.
```python
# Create a simple histogram
fig = px.histogram(
  			data_frame=revenues, 
            # Set up the x-axis
           	x="Revenue",
            # Set the number of bins
            nbins=5)

# Show the plot
fig.show()
```
### What color did we use?
### Coloring student scores bar graph
* Create a color scale list from red (255, 0, 0) to green (3, 252, 40).
* Set the color argument to the appropriate numerical column.
* Use my_scale as the color scale for the plot.
```python
# Create your own continuous color scale
my_scale = ["rgb(255, 0, 0)", "rgb(3, 252, 40)"]

# Create the bar plot
fig = px.bar(data_frame=student_scores, 
             x="student_name", y="score", title="Student Scores by Student",
             # Set the color variable and scale
             color="score",
                color_continuous_scale=my_scale
             )

# Show the plot
fig.show()
```
### Side-by-side revenue box plots with color
* Create a dictionary mapping each Industry to its RGB color.
* Create a box plot of revenues, using Revenue as the y-axis.
* Apply your industry color map to the plot.
```python
# Create the industry-color map
ind_color_map = {"Tech": "rgb(124, 250, 120)", "Oil": "rgb(112, 128,144)", 
                 "Pharmaceuticals": "rgb(137, 109,247)", "Professional Services": "rgb(255, 0, 0)"}

# Create a box plot
fig = px.box(
  			# Set the data and y variable
  			data_frame=revenues, y="Revenue",
  			# Set the color map 
			color="Industry",
			color_discrete_map=ind_color_map)

# Show the plot
fig.show()
```
### Revenue histogram with stacked bars
* Create a histogram of revenues, using Revenue as the x-axis.
* Apply the industry color map you created.
* Set the appropriate column for the color argument.
```python
# Create the industry-color map
ind_color_map = {"Tech": "rgb(124, 250, 120)", "Oil": "rgb(112, 128, 144)", 
                 "Pharmaceuticals": "rgb(137, 109, 247)", 
                 "Professional Services": "rgb(255, 0, 0)"}

# Create a histogram
fig = px.histogram(
  			# Set the data and x variable
  			data_frame=revenues, x="Revenue", nbins=5,
    		# Set the color map and variable
			color_discrete_map=ind_color_map,
			color="Industry")

# Show the plot
fig.show()
```
