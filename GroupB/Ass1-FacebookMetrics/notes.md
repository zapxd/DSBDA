## 2. What are the key features of Python?  
Answer:  
- Easy to learn, read, and maintain.  
- Extensive standard libraries.  
- Cross-platform compatibility.  
- Interactive and portable.  
- Extensible with low-level modules.  
- Provides database interfaces and GUI programming support.  

---

## 4. What is a DataFrame in Python?  
Answer:  
A DataFrame is a two-dimensional, size-mutable, and heterogeneous tabular data structure provided by the pandas library. It consists of rows and columns similar to a matrix or an SQL table.  

---

## 6. How do you create a subset of data using indexing in Pandas?  
Answer:  
Using the indexing operator:

```python
subset = df[['Type', 'Category']]
```

---

## 7. Explain the use of loc() function.  
Answer:  
loc() is used to access a group of rows and columns by labels or a boolean array.  
Example:

```python
subset = df.loc[0:3]
subset = df.loc[0:2, ['Type', 'Category']]
```

---

## 8. Explain the use of iloc() function.  
Answer:  
iloc() allows selection by row and column index positions.  
Example:

```python
subset = df.iloc[[0,1,3,6],[0,2]]
```

---

## 9. How can you merge two DataFrames in Pandas?  
Answer:  
Using the merge() function:

```python
merged = df1.merge(df2, on='Type')
```
or

```python
merged = pd.concat([df1, df2])
```

---

## 10. How can you sort a DataFrame?  
Answer:  
Sorting by a column:

```python
sorted_df = df.sort_values(by='Type')
```

Sorting descending:

```python
sorted_df = df.sort_values(by='Type', ascending=False)
```

---

## 11. How do you transpose a DataFrame?  
Answer:  
Using:

```python
df.transpose()
```
or simply:

```python
df.T
```

---

## 12. How do you check the shape of a DataFrame?  
Answer:

```python
df.shape
```
This returns a tuple (rows, columns).

---

## 13. What is the .melt() function in Pandas?  
Answer:  
The .melt() function reshapes a DataFrame from wide format to long format, turning columns into rows.  
Example:

```python
pd.melt(df, id_vars=['Type'], value_vars=['comment'])
```

---

## 14. Explain the .pivot() function.  
Answer:  
.pivot() reshapes data from a long format back to a wide format based on index/column values.  
Example:

```python
df_temp.pivot(index='foo', columns='bar', values='baz')
```

---

## 15. What is wide_to_long() transformation?  
Answer:  
wide_to_long() converts a wide-format DataFrame into a long-format one, especially when dealing with multiple variable columns.  

---

## 19. How do you merge two subsets on different columns (left 'like' and right 'share')?  
Answer:

```python
merged_df = pd.merge(df1, df2, left_on='like', right_on='share')
```

---

## 20. What happens when you transpose a DataFrame?  
Answer:  
Rows become columns and columns become rows.

---

## 21. How can you show a DataFrame in wide and long format?  
Answer:

- Wide format: Normal tabular form (rows as records, columns as features).  
- Long format: Using .melt(). Example:

```python
pd.melt(df, id_vars=['Type'], value_vars=['like', 'share'])
```

---

## 22. How to convert a DataFrame from wide to long and back from long to wide?  
Answer:

- Wide to long: Use .melt().  
- Long to wide: Use .pivot().  

---

## 1. What is Data Cleaning?  
Short Answer:  
Data cleaning is the process of identifying and correcting (or removing) errors, inconsistencies, and missing values from datasets to improve data quality.

---

## 2. What types of missing values exist?  
Short Answer:  
- MCAR (Missing Completely at Random)  
- MAR (Missing at Random)  
- MNAR (Missing Not at Random)

---

## 4. What is the difference between dropna() and fillna()?  
Short Answer:  
- dropna() removes missing rows/columns.  
- fillna() replaces missing values with a specific value like mean, median, or mode.

---

## 7. What are Outliers? How do you detect them?  
Short Answer:  
Outliers are extreme values that differ significantly from others.  
Detected using Boxplots, Z-score, or IQR method.

---

## 8. How to treat outliers?  
Short Answer:  
Options: Remove them, cap them (Winsorization), or transform them.

---

## 10. What is Encoding? When do you use it?  
Short Answer:  
Encoding is converting categorical variables into numeric form for ML models.  
Used LabelEncoder or OneHotEncoder.

---

## 11. What is Imputation?  
Short Answer:  
Filling missing data with estimated values like mean, median, mode, or prediction models.

---

## 12. What is Data Normalization vs Standardization?  
Short Answer:  
- Normalization scales data between 0 and 1.  
- Standardization transforms data to have mean = 0 and standard deviation = 1.

---
