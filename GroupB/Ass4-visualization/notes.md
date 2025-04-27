# Viva Questions on Data Visualization and Analysis

## 1. What is Data Visualization?

**Answer:**  
Data visualization is the graphical representation of data. It uses visual elements like charts, graphs, and maps to represent data. The goal is to make complex data more accessible, understandable, and usable by highlighting patterns, trends, and correlations in the data.

## 2. Why is Data Visualization important in Data Analysis?

**Answer:**  
Data visualization is important because it allows users to easily identify patterns, trends, and outliers in large datasets. It makes the analysis process more intuitive, helps in decision-making, and communicates insights effectively, especially to audiences that may not have a deep understanding of the raw data.

## 3. What are the benefits of using Data Visualization?

**Answer:**  
- Easier representation of complex data.
- Highlights good and bad performing areas.
- Explores relationships between data points.
- Identifies patterns and trends, even with larger datasets.
- Facilitates decision-making by providing clear insights.

## 4. Name two popular Python libraries used for Data Visualization and explain their key differences.

**Answer:**  
- **Matplotlib**: A 2D plotting library that is highly flexible and widely used for creating static, animated, and interactive visualizations. It works well with NumPy arrays and other SciPy stack libraries. However, its visuals may not always be aesthetically pleasing out of the box.

- **Seaborn**: A statistical data visualization library built on top of Matplotlib. It provides more aesthetically pleasing default themes and has built-in statistical functions to aid in data analysis. Seaborn simplifies the creation of complex visualizations with fewer lines of code.

## 5. What is a Pie Chart, and when would you use it?

**Answer:**  
A pie chart is a circular statistical graphic divided into slices to illustrate numerical proportions. Each slice represents a category’s contribution to the total. It is best used when showing parts of a whole, like market share or the percentage distribution of a dataset.

## 6. How do you create a Pie Chart in Python using Matplotlib? Explain the steps.

**Answer:**  
To create a pie chart in Python using Matplotlib:
1. Import `matplotlib.pyplot`.
2. Define the data and labels.
3. Use `plt.pie()` to plot the chart, passing the data, labels, and any other customization (like colors or explode).
4. Display the chart using `plt.show()`.
Example:
```python
import matplotlib.pyplot as plt
labels = ['Ozone', 'Solar.R', 'Wind', 'Temperature']
sizes = [data['Ozone'].mean(), data['Solar.R'].mean(), data['Wind'].mean(), data['Temp'].mean()]
colors = ['red', 'gold', 'purple', 'brown']
explode = (0.1, 0, 0, 0)
plt.pie(sizes, explode=explode, labels=labels, colors=colors, autopct='%1.1f%%', shadow=True, startangle=140)
plt.title('Average Data')
plt.show()
```

## 7. Explain the usage of a Bar Plot.

**Answer:**  
A bar plot is used to represent categorical data with rectangular bars. The length of each bar corresponds to the value of the category. Bar plots are useful for comparing different categories and can be oriented horizontally or vertically. 

## 8. How do you create a Bar Plot in Python using Matplotlib?

**Answer:**  
To create a bar plot in Python using Matplotlib:
1. Import `matplotlib.pyplot`.
2. Define the data and x-axis positions.
3. Use `plt.bar()` to create the bars.
4. Customize labels and titles, then use `plt.show()` to display the plot.
Example:
```python
import matplotlib.pyplot as plt
import numpy as np
data = pd.read_csv("airquality.csv")
h = data.iloc[1:21, 4]
y_pos = np.arange(len(h))
v = range(1, 21)
plt.bar(y_pos, h, align='center', alpha=0.5)
plt.xticks(y_pos, v)
plt.ylabel('Range')
plt.xlabel('Days')
plt.title('Temperature for 1st-20th May')
plt.show()
```

## 9. What is a Boxplot, and when should you use it?

**Answer:**  
A boxplot is a standardized way of displaying the distribution of data based on a five-number summary: minimum, first quartile (Q1), median, third quartile (Q3), and maximum. It helps identify outliers and understand the spread and symmetry of data. Boxplots are useful when comparing distributions across multiple categories or groups.

## 10. How do you create a Boxplot in Python using Matplotlib?

**Answer:**  
To create a boxplot:
1. Import `matplotlib.pyplot`.
2. Use `data.boxplot()` to plot the data by specifying the columns and grouping factors.
3. Display the plot using `plt.show()`.
Example:
```python
import matplotlib.pyplot as plt
import pandas as pd
data = pd.read_csv("mtcars.csv")
data.boxplot(by='cyl', column=['mpg'], grid=False)
plt.ylabel("Miles Per Gallon")
plt.xlabel("Number of Cylinders")
plt.title("Mileage Data")
plt.suptitle('')
plt.show()
```

## 11. What is a Histogram and when is it useful?

**Answer:**  
A histogram is a graphical representation of the distribution of a dataset. It divides the data into bins or intervals and plots the frequency of data points that fall within each bin. It is useful for understanding the distribution and spread of continuous numerical data.

## 12. How do you create a Histogram in Python using Matplotlib?

**Answer:**  
To create a histogram:
1. Import `matplotlib.pyplot`.
2. Use `plt.hist()` to define the data and the number of bins.
3. Display the histogram with `plt.show()`.
Example:
```python
import matplotlib.pyplot as plt
import pandas as pd
data = pd.read_csv("mtcars.csv")
h = data.iloc[:, -1]
plt.hist(h, bins='auto')
plt.title("Frequencies of Carburetors")
plt.ylabel("Frequency")
plt.xlabel("Number of Carburetors")
plt.show()
```

## 13. What is a Scatter Plot, and when should you use it?

**Answer:**  
A scatter plot is a graph that displays the relationship between two continuous variables. It uses Cartesian coordinates to represent data points. Scatter plots are useful for visualizing correlations, trends, and relationships between variables.

## 14. How do you create a Scatter Plot in Python using Seaborn?

**Answer:**  
To create a scatter plot using Seaborn:
1. Import `seaborn` and `matplotlib.pyplot`.
2. Use `sns.scatterplot()` to plot the data, specifying the x and y axes.
3. Display the plot with `plt.show()`.
Example:
```python
import seaborn as sns
import matplotlib.pyplot as plt
import pandas as pd
data = pd.read_csv("forestfires.csv")
sns.scatterplot(data=data, x='temp', y='humidity')
plt.show()
```

## 15. Explain what a Heatmap is and when it is useful.

**Answer:**  
A heatmap is a data visualization technique that uses color to represent values in a matrix or table. It is used to show the magnitude of data values in a matrix form, where color intensity represents the value of each cell. Heatmaps are useful for showing correlations, patterns, and trends within large datasets.

## 16. How do you create a Heatmap in Python using Seaborn?

**Answer:**  
To create a heatmap:
1. Import `seaborn` and `matplotlib.pyplot`.
2. Use `sns.heatmap()` to plot the correlation matrix or any other matrix-like data.
3. Display the heatmap with `plt.show()`.
Example:
```python
import seaborn as sns
import matplotlib.pyplot as plt
flights = sns.load_dataset("flights")
flights = flights.pivot("month", "year", "passengers")
sns.heatmap(flights)
plt.show()
```

## 17. What is a Word Cloud, and how is it created in Python?

**Answer:**  
A word cloud is a visual representation of text data where the size of each word reflects its frequency or importance. In Python, it can be created using the `WordCloud` class from the `wordcloud` library. Stopwords can be removed, and custom shapes can be used for better visualization.

## 18. How do you create a Word Cloud in Python?

**Answer:**  
To create a word cloud:
1. Import `WordCloud` from `wordcloud`.
2. Prepare the text data.
3. Generate the word cloud using `WordCloud().generate(text)`.
4. Save or display the word cloud with `plt.show()`.
Example:
```python
from wordcloud import WordCloud
import matplotlib.pyplot as plt
text = open("sampleWords.txt").read()
wordcloud = WordCloud().generate(text)
plt.imshow(wordcloud, interpolation="bilinear")
plt.axis('off')
plt.show()
```

## 19. What is the purpose of `remove_outliers` function?

**Answer:**  
The `remove_outliers` function is used to clean the data by identifying and removing data points that fall outside a specified range (based on the Interquartile Range, IQR). This is important to ensure the analysis is not distorted by extreme values that may not reflect the true data distribution.

## 20. What is the importance of Data Cleaning before visualization?

**Answer:**  
Data cleaning is important because it ensures that the data used for visualization is accurate, consistent, and free from errors or inconsistencies. Clean data leads to more meaningful and reliable visualizations, helping to extract valid insights and avoid misleading conclusions.

