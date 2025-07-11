# 🧪 Introduction to Exploratory Data Analysis (EDA) and Feature Engineering

Before building any models, it’s essential to explore and understand your dataset. **Exploratory Data Analysis (EDA)** gives insights into the data's structure, trends, and potential problems.

EDA combines **descriptive statistics** with **visualization techniques** to guide the next steps in your data science workflow.

---

## 🔍 What is EDA?

- EDA is the process of analyzing datasets to summarize their main characteristics using visual and quantitative methods.
- Think of it as your **first interaction with the data**—a way to understand its structure and contents before diving deeper.
- It helps answer:
  - Is the data complete and consistent?
  - Are there any outliers or anomalies?
  - What patterns or relationships exist?
- EDA often reveals whether you need more cleaning or data collection.

---

## 🛠 EDA Techniques

### 📊 Descriptive Statistics
- Measures like **mean**, **median**, **min**, **max**, and **standard deviation**
- **Correlations** between variables
- **Frequency counts** for categorical columns

### 📈 Visualization Tools
- **Histograms** – View distribution
- **Boxplots** – Spot outliers and data spread
- **Scatter plots** – See variable relationships
- **Bar charts** – Compare categories

---

## 🧰 Common EDA Tools

| Task                     | Tool              |
|--------------------------|-------------------|
| Data manipulation        | `pandas`          |
| Data visualization       | `matplotlib`, `seaborn` |

- **pandas**: Great for data wrangling and computing statistics
- **matplotlib**: Python’s core plotting library
- **seaborn**: Built on matplotlib, adds refined statistical visualizations

---

## 📌 Sample Histogram Visualization

```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

# Plotting a histogram of a feature
sns.histplot(data=df, x='feature_name')
plt.title('Feature Distribution')
plt.show()
```

---

## 🧪 DataFrame Sampling

Working with large or imbalanced datasets? Sampling helps manage size and improve training fairness.

### 🎯 Reasons to Sample:
- Reduce processing time
- Handle class imbalance
- Create manageable subsets

```python
df.sample(n=100, replace=False)  # Randomly sample 100 rows
df.iloc[:, -3:]                  # Select last 3 columns only
```

- `replace=False` ensures no duplicates
- `iloc[:, -3:]` retrieves the last 3 columns

> ✅ Use **stratified sampling** when preserving the class distribution is important (e.g., rare event detection).

---

## 📊 EDA with Visualizations

### 📦 Libraries for Visualization

| Library     | Description                                                              |
|-------------|--------------------------------------------------------------------------|
| `matplotlib`| Foundation for plotting in Python                                         |
| `pandas`    | Offers basic plotting with `.plot()` (built on matplotlib)               |
| `seaborn`   | Enhances matplotlib with high-level, statistical plots                   |

---

## 💡 Visualization Examples

### Line Plot for Time-Series Sales (Melted Data)

```python
plt.figure(figsize=(12, 6))
sns.lineplot(data=df_long, x='Month', y='Sales', hue='Product', marker='o')
plt.title('Monthly Sales by Product')
plt.xlabel('Month')
plt.ylabel('Sales ($)')
plt.legend(bbox_to_anchor=(1.05, 1), loc='upper left')
plt.tight_layout()
plt.show()
```

### Average Sales per Month (Bar Plot)

```python
plt.figure(figsize=(8, 6))
sns.barplot(data=df_long, x='Month', y='Sales', estimator='mean', ci='sd')
plt.title('Average Monthly Sales')
plt.xlabel('Month')
plt.ylabel('Mean Sales ($)')
plt.tight_layout()
plt.show()
```

### Sales Distribution per Month (Box Plot)

```python
plt.figure(figsize=(8, 6))
sns.boxplot(data=df_long, x='Month', y='Sales')
plt.title('Sales Spread by Month')
plt.xlabel('Month')
plt.ylabel('Sales ($)')
plt.tight_layout()
plt.show()
```

---

## 📚 Grouping and Aggregating

To extract deeper insights, grouping is often used to summarize data:

```python
df.groupby('Category').mean()
```

- Use `.groupby()` to find average sales per product, total counts per label, etc.
- Combine grouping with charts for clearer comparisons.

---

## ✅ Final Thoughts

Exploratory Data Analysis is your first opportunity to get to know your dataset. It helps with:

- Detecting patterns
- Identifying problems early
- Informing model decisions

Using `pandas`, `matplotlib`, and `seaborn` together allows for powerful and effective EDA workflows.
