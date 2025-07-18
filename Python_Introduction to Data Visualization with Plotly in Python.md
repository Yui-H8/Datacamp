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
