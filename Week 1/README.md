# Big-Data-Project
# BDA Task 1 – Superstore Sales Data Analysis

## Project Overview

This project performs **Business Data Analytics (BDA)** on the **Superstore dataset** using Python. The notebook explores sales, profit, categories, discounts, delivery time, data distribution, and correlations between numerical variables.

The analysis is performed using **Pandas, NumPy, Matplotlib, and Seaborn**.

## Dataset

The project uses the file:

```text
samplesuperstore.csv
```

The dataset is loaded using Pandas:

```python
df = pd.read_csv("/content/samplesuperstore.csv")
```

## Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Jupyter Notebook / Google Colab

## Libraries

```python
import pandas as pd
import numpy as np

import matplotlib.pyplot as plt
import seaborn as sns
```

## Data Preprocessing

The following preprocessing and data inspection operations are performed:

1. Load the Superstore CSV dataset.
2. Display the first few records using `head()`.
3. Check dataset information using `info()`.
4. Generate descriptive statistics using `describe()`.
5. Convert `Order Date` and `Ship Date` into datetime format.
6. Calculate delivery time using the difference between shipping and order dates.
7. Find unique values in the `Category` column.
8. Check for missing values using `isnull().sum()`.

### Delivery Days

A new column named `Delivery Days` is created:

```python
df['Delivery Days'] = (df['Ship Date'] - df['Order Date']).dt.days
```

This calculates the number of days taken between the order date and ship date.

## Data Analysis and Visualization

### 1. Sales by Category

The total sales for each category are calculated using `groupby()`:

```python
category_sales = df.groupby('Category')['Sales'].sum()
```

A bar plot is created to compare total sales across categories.

**Purpose:**
To identify and compare sales performance among different product categories.

### 2. Sales Distribution

A histogram is created using the Sales column.

**Purpose:**
To understand how sales values are distributed across the dataset.

### 3. Profit by Category

A Seaborn bar plot is used to compare profit across categories.

**Purpose:**
To determine which category generates higher profit.

### 4. Sales Distribution by Category

A bar plot is created using Category and Sales.

**Purpose:**
To compare sales values across different categories.

### 5. Profit Distribution

A box plot is created for the Profit column.

**Purpose:**

* Understand data distribution
* Identify the median
* Identify outliers
* Observe variation in profit

### 6. Profit Variation Across Categories

A box plot is created with Category and Profit.

**Purpose:**
To analyze how profit varies across different product categories and identify possible outliers.

### 7. Discount vs Profit Analysis

The unique discount values are identified and a scatter plot is created between Discount and Profit.

```python
sns.scatterplot(
    data=df,
    x="Discount",
    y="Profit"
)
```

**Purpose:**
To analyze the impact of discounts on profitability and observe whether higher discounts are associated with lower profit.

### 8. Correlation Analysis

Numerical columns are selected from the dataset:

```python
numeric_df = df.select_dtypes(include="number")
```

A correlation matrix is then calculated:

```python
corr = numeric_df.corr()
```

Finally, a correlation heatmap is created.

**Purpose:**
To identify relationships between numerical variables in the dataset.

## Visualizations Included

The notebook contains the following visualizations:

* Sales by Category – Bar Plot
* Sales Distribution – Histogram
* Profit by Category – Bar Plot
* Sales Distribution by Category – Bar Plot
* Profit Distribution – Box Plot
* Profit Variation Across Categories – Box Plot
* Impact of Discount on Profit – Scatter Plot
* Correlation Heatmap

## Project Objectives

The main objectives of this analysis are:

* To explore the Superstore dataset.
* To perform basic data preprocessing.
* To analyze sales and profit by category.
* To understand sales and profit distributions.
* To identify profit variation and outliers.
* To study the relationship between discount and profit.
* To analyze correlations between numerical variables.
* To represent analytical results through visualizations.

## Conclusion

This project demonstrates the use of Python libraries for **Business Data Analytics**. The Superstore dataset is explored through data inspection, preprocessing, statistical analysis, and visualization.

The analysis focuses on **sales, profit, category performance, discounts, delivery days, distributions, and correlations**, providing a basic understanding of the business data and its relationships.
