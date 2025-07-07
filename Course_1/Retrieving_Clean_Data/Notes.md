# Data Cleaning

## Why Data Cleaning is Important

- Decisions are driven by data.
- Key aspects of the machine learning workflow rely on clean data.
- Observations (rows in a dataset) that are not clean can misrepresent the relationship between features and targets.
- Labels must be accurate and consistently applied (e.g., in ImageNet).
- Algorithms estimate models assuming the data represents the real world.
- Features are the information we have for each observation.
- The model assumes the data is a true reflection of the real world.

> Messy data can lead to the *garbage-in, garbage-out* effect, producing unreliable outcomes.

> **The first step in any data project is data cleaning.**

---

## Common Data Challenges for Companies

- **Lack of data**: Insufficient quantity for meaningful analysis.
- **Too much data**: Requires systems to collect, organize, and manage it effectively.
- **Bad data**: Around 60% of companies report challenges managing data quality.

---

## What Is Messy Data?

Messy data can manifest in several ways:

- **Duplicate or unnecessary data**: Introduces noise and redundancy.
- **Inconsistent text or typos**: E.g., capitalization or spelling differences can result in misclassification.
- **Missing data**: Missing values across features can bias the dataset.
- **Outliers**: Extreme values can distort distributions.
- **Data sourcing issues**: Data pulled from multiple systems/databases may not align correctly.

---

## Duplicate or Unnecessary Data

- Watch out for duplicate values and investigate their origin.
- Review the features you're importing and filter data as needed.
- Avoid over-filtering—preserve access to the original data.
- Example: Duplicate images in a photo labeling task may degrade model quality.

---

# Data Cleaning: Handling Missing Values and Outliers

## Policies for Handling Missing Data

1. **Remove the data**  
   - Drop entire rows containing missing values.  
   - Quick and easy, but may introduce bias by removing informative records.

2. **Impute the data**  
   - Replace missing values with mean, median, or other statistics.  
   - Introduces uncertainty into the model, but retains the rows.

3. **Mask the data**  
   - Add a category such as "Unknown" or "Missing".  
   - Preserves rows but may still increase model complexity and uncertainty.

---

## Outliers

- An **outlier** is an observation significantly different from most others.
- Often these values are anomalies that don't reflect the typical pattern.
- Example: Sales data mostly between 10–50, with one entry of 3000, can skew the dataset.
- However, some outliers are **informative** and may reveal important insights.

---

## How to Find Outliers

### Visualization Tools:
- **Histograms**
- **Density plots**
- **Box plots**

### Mathematical Detection:
- Calculate **percentiles**: Q1 (25th), Q2 (50th), Q3 (75th)
- Compute **interquartile range (IQR)**:  
  `IQR = Q3 - Q1`
- Determine:
  - **Lower bound** = Q1 - 1.5 × IQR
  - **Upper bound** = Q3 + 1.5 × IQR
- Values outside this range can be considered outliers.

---

## Detecting Outliers Using Residuals

- **Residuals**: Differences between actual and predicted values. Large residuals can signal outliers or model errors.

### Types of Residuals:
- **Standardized residual**: Residual divided by its standard error.
- **Deleted residual**: Residual calculated by excluding the observation from the model.
- **Studentized residual**: Deleted residual divided by the residual standard error.

---

## Policies for Handling Outliers

- **Remove them**: Eliminates their effect but risks losing useful information.
- **Replace with mean/median**: Smooths data but may distort relationships.
- **Transform the variable**: Apply log, square root, or other transformations to reduce skew.
- **Predict the value**: Use regression or similar observations to estimate the correct value.
- **Keep them**: Use models robust to outliers (e.g., tree-based methods, robust regression).

---

## Final Notes

- **Data cleaning is critical for machine learning.**
- Messy data leads to biased or misleading results.
- Identifying and dealing with:
  - **Duplicates**
  - **Missing values**
  - **Outliers**  
  is essential for building reliable models.

> “Clean data is the foundation of good data science.”


## Associated notebooks


### **1. Data Reading Fundamentals (Course\_1\_ML\_NB\_1.ipynb & Course\_1\_ML\_NB\_2.ipynb)**

These notebooks introduce fundamental concepts of data reading in Python for Machine Learning. They cover how to connect to and read data from various sources, including CSV files and SQL databases (specifically SQLite). Key topics include:

  * **Establishing Database Connections:** Demonstrates connecting to different SQL databases using `sqlite3` and `pandas.io.sql`.
  * **Reading Data:** Explains how to load data into Pandas DataFrames from CSV files using `pd.read_csv` and from SQL tables using `pds.read_sql`.
  * **Exploring Data:** Provides initial steps for examining loaded data, such as checking data types (`.dtypes`) and inspecting the first few rows (`.head()`).

### **2. Data Cleaning Techniques (Course\_1\_ML\_NB\_3\_Data\_Cleaning\_Lab.ipynb)**

This notebook focuses on essential data cleaning techniques crucial for preparing raw data for machine learning analysis. It addresses common issues found in real-world datasets that can lead to inaccurate model predictions. The lab covers:

  * **Handling Missing Values:** Methods for identifying and addressing missing data points.
  * **Managing Duplicates:** Techniques for detecting and removing duplicate entries in the dataset.
  * **Outlier Treatment:** Strategies for identifying and handling outliers that can skew data analysis and model performance.
  * **Data Transformation:** Introduction to transforming skewed variables, such as using log transformations, to improve data distribution for modeling.
  * **Standardization and Normalization:** Basic concepts of scaling data to a standard range or distribution.




