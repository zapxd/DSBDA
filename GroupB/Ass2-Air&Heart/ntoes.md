## 1. What is the `unique()` function in Pandas?

**Answer:**  
The `unique()` function in Pandas is used to return an array of distinct unique values in a column. It helps to quickly identify the different categories or unique elements in a given column.

Example:
```python
df_categorical['Type'].unique()
```

---

## 2. How can you find the frequency distribution of a categorical column in Pandas?

**Answer:**  
To find the frequency distribution of a categorical column, you can use the `value_counts()` function. This function counts the occurrences of each unique value in the specified column.

Example:
```python
df_categorical['Grade'].value_counts()
```

---

## 3. How do you replace values in a column in Pandas?

**Answer:**  
You can use the `replace()` function to replace values in a specific column. For instance, you can replace 'Male' with 0 and 'Female' with 1 in the 'Gender' column.

Example:
```python
df_categorical['Gender'].replace({'Male': 0, 'Female': 1}, inplace=True)
```

---

## 4. What is the importance of error correction in data analysis?

**Answer:**  
Error correction is crucial in data analysis as it ensures that the data being analyzed is accurate and reliable. Errors can stem from various sources such as noise or cross-talk during data transmission. By identifying and correcting errors, we ensure that the analysis yields correct results.

---

## 5. What is the significance of checking the min and max values in continuous variables?

**Answer:**  
Checking the min and max values of continuous variables helps identify whether the data falls within an expected range. This step is important to detect anomalies such as outliers or incorrect data entries.

---

## 6. How can you find missing values in a DataFrame?

**Answer:**  
You can find missing values in a DataFrame using the `isna().sum()` method, which returns the number of missing values in each column. You can also calculate the percentage of missing values by dividing the number of missing values by the total length of the DataFrame.

Example:
```python
df.isna().sum()
percent_missing = df.isnull().sum() * 100 / len(df)
percent_missing.sort_values(ascending=False)
```

---

## 7. What is the purpose of normalizing data?

**Answer:**  
Normalization is the process of scaling the data into a specific range, usually between 0 and 1. This is done to ensure that different features in the data contribute equally to the model, especially when the features have different units or ranges.

---

## 8. What is the difference between simple linear regression and multiple linear regression?

**Answer:**  
- **Simple Linear Regression:** This is used when there is only one independent variable (X) to predict the dependent variable (Y).
- **Multiple Linear Regression:** This is used when there are multiple independent variables (X1, X2, X3, ...) to predict the dependent variable (Y).

---

## 9. How do you evaluate a regression model?

**Answer:**  
The performance of a regression model is typically evaluated using metrics like **R-squared** and **Mean Squared Error (MSE)**. Visualization techniques such as scatter plots and regression lines can also be used to visually inspect the fit of the model.

---

## 10. What is R-squared and how is it used to evaluate regression models?

**Answer:**  
R-squared is a statistical measure that represents the proportion of the variance for the dependent variable that's explained by the independent variables in a regression model. A higher R-squared value indicates a better fit of the model to the data.

---

## 11. Explain the significance of Polynomial Regression.

**Answer:**  
Polynomial regression is a type of regression that models the relationship between the independent variable and the dependent variable as an nth-degree polynomial. It is used when the relationship between the variables is non-linear.

---

## 12. What is the importance of model evaluation using visualization?

**Answer:**  
Visualization helps in understanding the performance of the model by showing how well the predicted values match the actual values. It provides insights into the model's accuracy, errors, and patterns that might not be obvious from numerical metrics alone.

---

## 13. How would you group the AQI by city and calculate the average AQI per city?

**Answer:**  
You can use the `groupby()` function along with `mean()` to group the AQI values by city and calculate the average AQI.

Example:
```python
x = pd.DataFrame(df.groupby(['City'])[['AQI']].mean().sort_values(by='AQI', ascending=False).head(10))
x = x.reset_index('City')
```

---

## 14. How do you handle missing values in Pandas?

**Answer:**  
You can handle missing values by either filling them using the `fillna()` function with appropriate values (e.g., mean, median, or mode) or by dropping them using the `dropna()` function.

Example:
```python
df['column_name'].fillna(df['column_name'].mode()[0], inplace=True)
```

---

## 15. How do you remove duplicates in a DataFrame?

**Answer:**  
To remove duplicates in a DataFrame, you can use the `drop_duplicates()` function.

Example:
```python
df = df.drop_duplicates()
```

---

## 16. What are outliers and how do you detect them?

**Answer:**  
Outliers are values that differ significantly from the rest of the data. They can be detected using methods such as Boxplots, Z-score, or the IQR (Interquartile Range) method.

---

## 17. How do you remove outliers from a DataFrame?

**Answer:**  
You can remove outliers by calculating the Interquartile Range (IQR) and filtering out values that fall outside the acceptable range.

Example:
```python
def remove_outliers(column):
    Q1 = column.quantile(0.25)
    Q3 = column.quantile(0.75)
    IQR = Q3 - Q1
    threshold = 1.5 * IQR
    outlier_mask = (column < Q1 - threshold) | (column > Q3 + threshold)
    return column[~outlier_mask]
```

---

## 18. How do you apply Label Encoding to categorical columns?

**Answer:**  
You can apply Label Encoding to categorical columns using the `LabelEncoder` from scikit-learn, which converts categorical values into numerical form.

Example:
```python
from sklearn.preprocessing import LabelEncoder
encoder = LabelEncoder()
df['column_name'] = encoder.fit_transform(df['column_name'])
```

---

## 19. How do you train a linear regression model?

**Answer:**  
You can train a linear regression model using the `LinearRegression()` class from scikit-learn. You first need to separate the input and output variables, split the data into training and testing sets, and then fit the model using the training data.

Example:
```python
from sklearn.linear_model import LinearRegression
model = LinearRegression()
model.fit(X_train, y_train)
```

---

## 20. What is the purpose of train-test splitting in machine learning?

**Answer:**  
The purpose of train-test splitting is to evaluate the performance of a model. The training set is used to fit the model, while the test set is used to validate its performance on unseen data. This helps in assessing how well the model generalizes.

---

## 21. What are the benefits of dropping unnecessary columns in a DataFrame?

**Answer:**  
Dropping unnecessary columns helps in reducing the dimensionality of the data, which can improve model performance, reduce computational load, and prevent overfitting by removing irrelevant features.

---

## 22. What is the significance of handling missing values before data analysis?

**Answer:**  
Handling missing values is important because they can distort the results of the analysis. Missing data can lead to biased models, incorrect conclusions, and reduced accuracy. Handling them appropriately ensures reliable and accurate analysis results.

---
10. What is Encoding? When do you use it?
Short Answer:
Encoding is converting categorical variables into numeric form for ML models.
Used LabelEncoder or OneHotEncoder.
11. What is Imputation?
Short Answer:
Filling missing data with estimated values like mean, median, mode, or prediction
models.
12. What is Data Normalization vs Standardization?
Short Answer:
Normalization scales data between 0 and 1.
Standardization transforms data to have mean = 0 and standard deviation = 1.
