# Guide to Python Data & ML Libraries

## Table of Contents
1. [Introduction](#introduction)
2. [NumPy](#numpy)
   - Overview
   - Key Functions & Methods
3. [pandas](#pandas)
   - Overview
   - Data Structures
   - Essential Methods
4. [Matplotlib](#matplotlib)
   - Overview
   - Plot Types
   - Customization
5. [Seaborn](#seaborn)
   - Overview
   - Key Features
   - Example Plots
6. [scikit-learn](#scikit-learn)
   - Overview
   - Key Modules
   - Important Functions
7. [TensorFlow](#tensorflow)
   - Overview
   - Core Components
   - Building Models
8. [Other Essential Libraries](#other-essential-libraries)
   - Statsmodels
   - Plotly
   - SciPy
   
---

## Introduction
This guide provides an extensive breakdown of essential Python libraries for data manipulation, visualization, and machine learning. These libraries are widely used in academia and industry for processing large datasets, building machine learning models, and creating insightful visualizations.

---

## NumPy
### Overview
NumPy (Numerical Python) is the core library for numerical computing in Python. It provides support for multi-dimensional arrays and matrices, along with mathematical functions to operate on these data structures.

### Key Functions & Methods
- **Array Creation**
  - `np.array()` - Create an array
  - `np.zeros()` - Create an array filled with zeros
  - `np.ones()` - Create an array filled with ones
  - `np.eye()` - Identity matrix
  - `np.linspace()` - Generate linearly spaced values
  
- **Array Operations**
  - `np.add()`, `np.subtract()`, `np.multiply()`, `np.divide()` - Basic arithmetic operations
  - `np.dot()` - Matrix multiplication
  - `np.linalg.inv()` - Inverse of a matrix
  - `np.linalg.eig()` - Eigenvalues and eigenvectors

- **Statistical Functions**
  - `np.mean()`, `np.median()`, `np.std()`, `np.var()` - Compute statistical metrics
  - `np.percentile()` - Compute percentiles

---

## pandas
### Overview
pandas is a powerful library for data manipulation and analysis. It provides data structures like Series and DataFrame to handle structured data efficiently.

### Data Structures (mutable)
- `pandas.Series` - One-dimensional labeled array
- `pandas.DataFrame` - Two-dimensional labeled data structure

### Essential Methods
- **Reading & Writing Data**
  - `pd.read_csv()` - Read CSV files
  - `df.to_csv()` - Save DataFrame to CSV
  - `pd.read_excel()`, `df.to_excel()` - Read/write Excel files
  
- **Data Inspection**
  - `df.head()`, `df.tail()` - View first/last rows
  - `df.info()` - Summary of DataFrame
  - `df.describe()` - Statistical summary

- **Data Cleaning**
  - `df.dropna()` - Remove missing values
  - `df.fillna()` - Fill missing values
  - `df.replace()` - Replace values
  
- **Data Transformation**
  - `df.groupby()` - Group data
  - `df.pivot_table()` - Create pivot tables
  - `df.melt()` - Reshape data

---

## Matplotlib
### Overview
Matplotlib is a visualization library used for creating static, animated, and interactive plots.

### Plot Types
- `plt.plot()` - Line plot
- `plt.scatter()` - Scatter plot
- `plt.bar()` - Bar plot
- `plt.hist()` - Histogram
- `plt.boxplot()` - Box plot

### Customization
- `plt.xlabel()`, `plt.ylabel()`, `plt.title()` - Labels & title
- `plt.legend()` - Add legend
- `plt.grid()` - Add gridlines

---

## Seaborn
### Overview
Seaborn is built on top of Matplotlib and provides a high-level API for statistical data visualization.

### Key Features
- `sns.pairplot()` - Pairwise relationships
- `sns.heatmap()` - Correlation matrix visualization
- `sns.violinplot()` - Distribution visualization

### Example Plots
```python
import seaborn as sns
import matplotlib.pyplot as plt

df = sns.load_dataset('iris')
sns.pairplot(df, hue='species')
plt.show()
```

---

## scikit-learn
### Overview
scikit-learn is the most widely used machine learning library in Python.

### Key Modules
- `sklearn.preprocessing` - Data preprocessing
- `sklearn.model_selection` - Train-test splitting, cross-validation
- `sklearn.ensemble` - Random Forest, Gradient Boosting
- `sklearn.svm` - Support Vector Machines

### Important Functions
- `train_test_split()` - Split data into train and test sets
- `StandardScaler()` - Normalize data
- `RandomForestClassifier()` - Train a Random Forest model

---

## TensorFlow
### Overview
TensorFlow is a deep learning framework developed by Google.

### Core Components
- **Tensors** - Multi-dimensional arrays
- **Graphs & Sessions** - Computational graphs
- **Keras API** - High-level API for deep learning

### Building Models
```python
import tensorflow as tf
from tensorflow import keras

model = keras.Sequential([
    keras.layers.Dense(64, activation='relu'),
    keras.layers.Dense(1, activation='sigmoid')
])
model.compile(optimizer='adam', loss='binary_crossentropy', metrics=['accuracy'])
```

---

## Other Essential Libraries
### Statsmodels
- Used for statistical modeling and hypothesis testing
- `statsmodels.api.OLS()` - Ordinary Least Squares regression

### Plotly
- Interactive visualizations
- `plotly.express.scatter()` - Create scatter plots

### SciPy
- Advanced scientific computing
- `scipy.optimize.minimize()` - Optimization problems

---

## Conclusion
This document provides an extensive overview of Python's most powerful libraries for data analysis, visualization, and machine learning. Mastering these libraries will help in tackling complex data problems efficiently.

For more information, refer to:
- [NumPy Documentation](https://numpy.org/doc/)
- [pandas Documentation](https://pandas.pydata.org/docs/)
- [Matplotlib Documentation](https://matplotlib.org/stable/contents.html)
- [Seaborn Documentation](https://seaborn.pydata.org/)
- [scikit-learn Documentation](https://scikit-learn.org/stable/)
- [TensorFlow Documentation](https://www.tensorflow.org/)

Happy coding!

