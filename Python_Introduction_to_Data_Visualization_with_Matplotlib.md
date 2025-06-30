# Introduction to Data Visualization with Matplotlib
---
### Using the matplotlib.pyplot interface
* Import the matplotlib.pyplot API, using the conventional name plt.
* Create Figure and Axes objects using the plt.subplots function.
* Show the results, an empty set of axes, using the plt.show function.

```python
# Import the matplotlib.pyplot submodule and name it plt
import matplotlib.pyplot as plt

# Create a Figure and an Axes with plt.subplots
fig, ax = plt.subplots()

# Call the show function to show the result
plt.show()
```
### Adding data to an Axes object
* Import the matplotlib.pyplot submodule as plt.
* Create a Figure and an Axes object by calling plt.subplots.
* Add data from the seattle_weather DataFrame by calling the Axes plot method.
* Add data from the austin_weather DataFrame in a similar manner and call plt.show to show the results.
```python
# Import the matplotlib.pyplot submodule and name it plt
import matplotlib.pyplot as plt

# Create a Figure and an Axes with plt.subplots
fig, ax = plt.subplots()

# Plot MLY-PRCP-NORMAL from seattle_weather against the MONTH
ax.plot(seattle_weather["MONTH"], seattle_weather["MLY-PRCP-NORMAL"])

# Plot MLY-PRCP-NORMAL from austin_weather against MONTH
ax.plot(austin_weather["MONTH"], austin_weather["MLY-PRCP-NORMAL"])

# Call the show function
plt.show()
```
### Customizing data appearance
* Call ax.plot to plot "MLY-PRCP-NORMAL" against "MONTHS" in both DataFrames.
* Pass the color key-word arguments to these commands to set the color of the Seattle data to blue ('b') and the Austin data to red ('r').
* Pass the marker key-word arguments to these commands to set the Seattle data to circle markers ('o') and the Austin markers to triangles pointing downwards ('v').
* Pass the linestyle key-word argument to use dashed lines for the data from both cities ('--').
```python
# Plot Seattle data, setting data appearance
ax.plot(seattle_weather["MONTH"], seattle_weather["MLY-PRCP-NORMAL"], color = 'b', marker = 'o', linestyle = '--')

# Plot Austin data, setting data appearance
ax.plot(austin_weather["MONTH"], austin_weather["MLY-PRCP-NORMAL"], color = 'r', marker = 'v', linestyle = '--')

# Call show to display the resulting plot
plt.show()
```
### Customizing axis labels and adding titles
* Use the set_xlabel method to add the label: "Time (months)".
* Use the set_ylabel method to add the label: "Precipitation (inches)".
* Use the set_title method to add the title: "Weather patterns in Austin and Seattle".
```python
ax.plot(seattle_weather["MONTH"], seattle_weather["MLY-PRCP-NORMAL"])
ax.plot(austin_weather["MONTH"], austin_weather["MLY-PRCP-NORMAL"])

# Customize the x-axis label
ax.set_xlabel("Time (months)")

# Customize the y-axis label
ax.set_ylabel("Precipitation (inches)")

# Add the title
ax.set_title("Weather patterns in Austin and Seattle")

# Display the figure
plt.show()
```
---
### Creating small multiples with plt.subplots
* Create a Figure and an array of subplots with 2 rows and 2 columns.
* Addressing the top left Axes as index 0, 0, plot the Seattle precipitation.
* In the top right (index 0,1), plot Seattle temperatures.
* In the bottom left (1, 0) and bottom right (1, 1) plot Austin precipitations and temperatures.
```python
# Create a Figure and an array of subplots with 2 rows and 2 columns
fig, ax = plt.subplots(2, 2)

# Addressing the top left Axes as index 0, 0, plot month and Seattle precipitation
ax[0, 0].plot(seattle_weather["MONTH"], seattle_weather["MLY-PRCP-NORMAL"])

# In the top right (index 0,1), plot month and Seattle temperatures
ax[0, 1].plot(seattle_weather["MONTH"], seattle_weather["MLY-TAVG-NORMAL"])

# In the bottom left (1, 0) plot month and Austin precipitations
ax[1, 0].plot(austin_weather["MONTH"], austin_weather["MLY-PRCP-NORMAL"])

# In the bottom right (1, 1) plot month and Austin temperatures
ax[1, 1].plot(austin_weather["MONTH"], austin_weather["MLY-TAVG-NORMAL"])
plt.show()
```
### Small multiples with shared y axis
