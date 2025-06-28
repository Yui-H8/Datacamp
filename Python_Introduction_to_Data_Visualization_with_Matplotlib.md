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
