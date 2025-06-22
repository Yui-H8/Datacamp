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
