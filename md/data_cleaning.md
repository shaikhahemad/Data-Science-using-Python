
# Data Cleaning in Python

Data cleaning is a critical step in the data science process to ensure that your dataset is accurate, consistent, and ready for analysis. In this comprehensive guide, we'll explore various advanced data cleaning techniques using Python and popular libraries such as Pandas and Scikit-Learn.

## Table of Contents
- Handling Missing Data
- Dealing with Duplicates 
- Outlier Detection and Handling
- Data Type Conversion
- Handling Inconsistent Data
- Date and Time Parsing
- Handling Text Data (NLP) - Advanced

## Handling Missing Data

Dealing with missing data is a common challenge. Pandas provides several tools for this task:

```python
import pandas as pd

# Check for missing values
df.isnull().sum()

# Drop rows with missing values
df.dropna()

# Fill missing values with a specific value
df.fillna(value)
```

## Dealing with Duplicates

Identifying and handling duplicates is essential for accurate analysis:

```python
# Check for duplicates
df.duplicated().sum()

# Drop duplicate rows
df.drop_duplicates()
```

## Outlier Detection and Handling

Outliers can significantly impact analysis. Use statistical methods or visualization to identify and handle outliers:

```python
from scipy.stats import zscore

# Identify outliers using Z-score
z_scores = zscore(df[['numeric_column']])
outliers = (z_scores > 3) | (z_scores < -3)

# Remove outliers
df = df[~outliers]
```

## Data Type Conversion

Ensuring appropriate data types is crucial for analysis:

```python
# Convert a column to a different data type
df['column_name'] = df['column_name'].astype(new_data_type)
```

## Handling Inconsistent Data

Addressing inconsistencies in categorical data is important:

```python
# Mapping categories to consistent values
df['category_column'] = df['category_column'].map({'old_value': 'new_value'})
```

## Date and Time Parsing

Proper parsing of date and time data is crucial for accurate analysis:

```python
# Convert string to datetime
df['date_column'] = pd.to_datetime(df['date_column'])

# Extract components (year, month, day)
df['year'] = df['date_column'].dt.year
```

## Handling Text Data (NLP) - Advanced

For advanced text data cleaning, use natural language processing (NLP) techniques:

```python
from nltk.tokenize import word_tokenize
from nltk.stem import PorterStemmer

# Tokenize and stem words
df['text_column'] = df['text_column'].apply(lambda x: [PorterStemmer().stem(word) for word in word_tokenize(x)])
```

This all-in-one guide covers fundamental and advanced data cleaning techniques in Python using Pandas and other libraries. Adapt these methods based on the characteristics of your dataset and the requirements of your analysis.

