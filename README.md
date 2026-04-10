# Pandas

A comprehensive learning repository for Pandas, the essential Python library for data manipulation and analysis. This collection contains structured notebooks covering everything from basic DataFrame operations to advanced data transformation techniques.

## Repository Structure

```
Pandas/
├── Pandas 1.ipynb - Pandas 7.ipynb    # Core concept notebooks
├── Pandas 10 Tasks.ipynb              # Practice exercises
├── Notes/                              # Detailed topic notes
└── Sample .CSV Data Files/             # Practice datasets
```

## Curriculum Overview

### Core Notebooks

| Notebook | Topics Covered |
|----------|----------------|
| `Pandas 1.ipynb` | Introduction, Series, DataFrame creation |
| `Pandas 2.ipynb` | Data selection, indexing, slicing |
| `Pandas 3.ipynb` | Data inspection, info, describe |
| `Pandas 4.ipynb` | Filtering, conditional selection |
| `Pandas 5.ipynb` | Data modification, adding/removing columns |
| `Pandas 6.ipynb` | Sorting, grouping, aggregation |
| `Pandas 7.ipynb` | Date/time operations, time series |

### Notes Directory

| Notebook | Content |
|----------|---------|
| `1) Pandas Series and Data Frame.ipynb` | Fundamentals of Series and DataFrame |
| `2) Pandas Basic.ipynb` | Basic operations and methods |
| `4) Filtering and Updating in pandas.ipynb` | Data filtering techniques |
| `5) Add, Remove and Merge in data.ipynb` | Data manipulation operations |
| `6) Sorting and Grouping.ipynb` | Sort operations and groupby |
| `7) Date & Time in Pandas.ipynb` | Datetime handling |
| `8) Read and Write in pandas.ipynb` | File I/O operations |

### Practice Materials
- `Pandas 10 Tasks.ipynb` - Hands-on exercises
- `Data_Analysis_Assignment_Pandas_NumPy_Matplotlib.docx` - Comprehensive assignment

## Core Concepts

### Series and DataFrames

```python
import pandas as pd

# Creating a Series
s = pd.Series([1, 2, 3, 4, 5])

# Creating a DataFrame
df = pd.DataFrame({
    'Name': ['Alice', 'Bob', 'Charlie'],
    'Age': [25, 30, 35],
    'City': ['NYC', 'LA', 'Chicago']
})
```

### Data Selection

```python
# Column selection
df['Name']           # Single column
df[['Name', 'Age']]  # Multiple columns

# Row selection
df.loc[0]            # By label
df.iloc[0]           # By position
df.loc[0:2, 'Name']  # Specific rows and columns
```

### Filtering

```python
# Boolean indexing
df[df['Age'] > 25]

# Multiple conditions
df[(df['Age'] > 25) & (df['City'] == 'NYC')]

# Query method
df.query('Age > 25 and City == "NYC"')
```

### Data Manipulation

```python
# Adding columns
df['Country'] = 'USA'

# Applying functions
df['Age_Group'] = df['Age'].apply(lambda x: 'Young' if x < 30 else 'Adult')

# Removing columns
df.drop('Country', axis=1, inplace=True)
```

### Grouping and Aggregation

```python
# GroupBy operations
df.groupby('City').mean()
df.groupby('City').agg({
    'Age': ['mean', 'min', 'max'],
    'Salary': 'sum'
})

# Pivot tables
pd.pivot_table(df, values='Salary', index='City', columns='Department')
```

### Sorting

```python
# Sort by values
df.sort_values('Age', ascending=False)

# Sort by multiple columns
df.sort_values(['City', 'Age'], ascending=[True, False])

# Sort by index
df.sort_index()
```

### Merging and Joining

```python
# Merge DataFrames
pd.merge(df1, df2, on='ID', how='inner')

# Concatenate
pd.concat([df1, df2], axis=0)  # Vertical
pd.concat([df1, df2], axis=1)  # Horizontal
```

### Date and Time

```python
# Convert to datetime
df['Date'] = pd.to_datetime(df['Date'])

# Extract components
df['Year'] = df['Date'].dt.year
df['Month'] = df['Date'].dt.month
df['DayOfWeek'] = df['Date'].dt.dayofweek

# Date range
pd.date_range(start='2024-01-01', periods=10, freq='D')
```

### File I/O

```python
# Reading data
df = pd.read_csv('data.csv')
df = pd.read_excel('data.xlsx')
df = pd.read_json('data.json')

# Writing data
df.to_csv('output.csv', index=False)
df.to_excel('output.xlsx', index=False)
```

## Sample Datasets

The `Sample .CSV Data Files/` directory includes practice datasets for:
- Customer data analysis
- Sales transactions
- Employee records
- Time series data

## Learning Path

### Week 1: Fundamentals
- Pandas 1: Series and DataFrame basics
- Notes 1-2: Core concepts

### Week 2: Selection and Filtering
- Pandas 2-3: Indexing and inspection
- Pandas 4: Filtering techniques

### Week 3: Manipulation
- Pandas 5: Adding, removing, updating
- Notes 4-5: Data transformation

### Week 4: Analysis
- Pandas 6: Grouping and aggregation
- Notes 6: Sorting and grouping

### Week 5: Advanced Topics
- Pandas 7: Date/time operations
- Notes 7-8: Time series and I/O

### Week 6: Practice
- Pandas 10 Tasks
- Complete assignment

## Common Operations Cheat Sheet

| Operation | Code |
|-----------|------|
| View first rows | `df.head()` |
| View last rows | `df.tail()` |
| Shape of data | `df.shape` |
| Column names | `df.columns` |
| Data types | `df.dtypes` |
| Summary stats | `df.describe()` |
| Info | `df.info()` |
| Missing values | `df.isnull().sum()` |
| Drop duplicates | `df.drop_duplicates()` |
| Fill missing | `df.fillna(value)` |
| Rename columns | `df.rename(columns={'old': 'new'})` |
| Reset index | `df.reset_index()` |

## Installation

```bash
git clone https://github.com/krish2248/Pandas.git
cd Pandas

# Install dependencies
pip install pandas jupyter

# Launch notebooks
jupyter notebook
```

## Requirements

- Python 3.8+
- Pandas 1.3+
- Jupyter Notebook
- NumPy (dependency)

## Best Practices

1. **Chain operations** for cleaner code
2. **Use vectorized operations** instead of loops
3. **Set appropriate data types** for memory efficiency
4. **Use categorical dtype** for repeated strings
5. **Avoid SettingWithCopyWarning** by using .loc

## Resources

- [Pandas Documentation](https://pandas.pydata.org/docs/)
- [10 Minutes to Pandas](https://pandas.pydata.org/docs/user_guide/10min.html)
- [Pandas Cheat Sheet](https://pandas.pydata.org/Pandas_Cheat_Sheet.pdf)

## Contributing

Contributions welcome:
- Additional practice notebooks
- Real-world dataset examples
- Documentation improvements

## License

MIT License
