# Introduction to Seaborn
---
### Making a scatter plot with lists
* Import Matplotlib and Seaborn using the standard naming convention.
```python
# Import Matplotlib and Seaborn
import matplotlib.pyplot as plt
import seaborn as sns
```
### Making a scatter plot with lists
* Create a scatter plot of GDP (gdp) vs. number of phones per 1000 people (phones).
```python
# Import Matplotlib and Seaborn
import matplotlib.pyplot as plt
import seaborn as sns

# Create scatter plot with GDP on the x-axis and number of phones on the y-axis
sns.scatterplot(x=gdp, y=phones)
```
* Create a scatter plot of GDP (gdp) vs. number of phones per 1000 people (phones).
```python
# Import Matplotlib and Seaborn
import matplotlib.pyplot as plt
import seaborn as sns

# Create scatter plot with GDP on the x-axis and number of phones on the y-axis
sns.scatterplot(x=gdp, y=phones)
```
* Display the plot.
```python
# Import Matplotlib and Seaborn
import matplotlib.pyplot as plt
import seaborn as sns

# Create scatter plot with GDP on the x-axis and number of phones on the y-axis
sns.scatterplot(x=gdp, y=phones)

# Show plot
plt.show()
```
* Change the scatter plot so it displays the percent of the population that can read and write (percent_literate) on the y-axis.
```python
# Import Matplotlib and Seaborn
import matplotlib.pyplot as plt
import seaborn as sns

# Change this scatter plot to have percent literate on the y-axis
sns.scatterplot(x=gdp, y=percent_literate)

# Show plot
plt.show()
```
### Making a count plot with a list
* Import Matplotlib and Seaborn using the standard naming conventions.
* Use Seaborn to create a count plot with region on the y-axis.
* Display the plot.
```python
# Import Matplotlib and Seaborn
import matplotlib.pyplot as plt
import seaborn as sns

# Create count plot with region on the y-axis
sns.countplot(y=region)

# Show plot
plt.show()
```
---
### "Tidy" vs. "untidy" data
* Read the csv file located at csv_filepath into a DataFrame named df.
* Print the head of df to show the first five rows.
```python
# Import pandas
import pandas as pd

# Create a DataFrame from csv file
df = pd.read_csv(csv_filepath)

# Print the head of df
print(df.head())
```
### Making a count plot with a DataFrame
* Import Matplotlib, pandas, and Seaborn using the standard names.
* Create a DataFrame named df from the csv file located at csv_filepath.
* Use the countplot() function with the x= and data= arguments to create a count plot with the "Spiders" column values on the x-axis.
* Display the plot.
```python
# Import Matplotlib, pandas, and Seaborn
import matplotlib.pyplot as plt
import pandas as pd
import seaborn as sns

# Create a DataFrame from csv file
df = pd.read_csv(csv_filepath)

# Create a count plot with "Spiders" on the x-axis
sns.countplot(x="Spiders", data= df)

# Display the plot
plt.show()
```
---
### Hue and scatter plots
* Create a scatter plot with "absences" on the x-axis and final grade ("G3") on the y-axis using the DataFrame student_data. Color the plot points based on "location" (urban vs. rural).
```pyhton
# Import Matplotlib and Seaborn
import matplotlib.pyplot as plt
import seaborn as sns

# Create a scatter plot of absences vs. final grade
sns.scatterplot(x = "absences", 
                y = "G3", 
                hue = "location", 
                data = student_data)

# Show plot
plt.show()
```
* Make "Rural" appear before "Urban" in the plot legend.
```python
# Import Matplotlib and Seaborn
import matplotlib.pyplot as plt
import seaborn as sns

# Change the legend order in the scatter plot
sns.scatterplot(x="absences", y="G3", 
                data=student_data, 
                hue="location",
                hue_order = ["Rural", "Urban"])

# Show plot
plt.show()
```
### Hue and count plots
* Fill in the palette_colors dictionary to map the "Rural" location value to the color "green" and the "Urban" location value to the color "blue".
* Create a count plot with "school" on the x-axis using the student_data DataFrame.
* Add subgroups to the plot using "location" variable and use the palette_colors dictionary to make the location subgroups green and blue.
```python
# Import Matplotlib and Seaborn
import matplotlib.pyplot as plt
import seaborn as sns

# Create a dictionary mapping subgroup values to colors
palette_colors = {"Rural": "green", "Urban": "blue"}

# Create a count plot of school with location subgroups
sns.countplot( x = "school",
 hue = "location" ,
 palette = palette_colors,
 data = student_data)


# Display plot
plt.show()
```
