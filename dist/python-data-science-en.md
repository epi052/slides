# {{title}}

## Presentation and code

Presentations available at: https://karuga.eu/courses-presentations

Code available at: https://github.com/marko-knoebl/courses-code

## Your Trainer

Marko Knöbl

- Frontend Web-Development
  - JavaScript
  - React, Angular
- Programming
  - Python, JavaScript

## Introduction of Participants

- Name
- Company
- Current Projects
- Prior Knowledge
- Expectations

## Organizational

- Duration
- Breaks
- Materials
- Questions, Feedback?

# Packages

## Python packages for data science

- _Jupyter_ & _IPython_: interactive Python environments
- _NumPy_: library for efficient processing of numerical data
- _Pandas_: library for data analysis, based on NumPy
- _Matplotlib_: library for data visualization
- _Scikit-Learn_: library for machine learning, based on NumPy

## Anaconda

Anaconda = Python distribution that includes many pre-installed packages and developer tools

Takes ~ 3 GB of disk space

## Conda

Conda = management tool for Python packages and environments, used by Anaconda

Enables installation of multiple versions of Python and Python packages

Particularly useful for external libraries that are written in a compiled language

## Miniconda

_Miniconda_ = distribution that only includes Python and Conda, all other packages must be installed via Conda

Initially takes ~ 250 MB of disk space

# Jupyter & IPython

## IPython

IPython = advanced interactive Python console, supports features like autocompletion

## Jupyter notebooks

Jupyter notebook = interactive graphical Python environment, includes IPython functionalities

Jupyter is browser-based; the backend can be run on the local machine or can be hosted on a server

## Jupyter notebooks - online

Try Jupyter online:

### Google Colab (Google account needed)

- Go to https://colab.research.google.com
- Select _File_ - _New Python 3 Notebook_

### Binder (limited sessions)

- Go to https://jupyter.org/try
- Select _Try Jupyter with Python_
- wait ...
- Select _File_ - _New Notebook_ - _Python 3_

## Jupyter notebooks - locally

Launching Jupyter: Entry _Jupyter Notebook_ in the start menu

Stopping Jupyter: Press _Quit_ in the top right corner of the directory tree view (usually under http://localhost:8888/tree)

## Notebook files

Jupyter notebook files can be created via _new_ - _Notebook: Python 3_

Will be saved under _notebook.ipynb_

_Ipynb_: File format that can contain Python code, outputs, text documentation

## Writing and evaluating code

Write code into a cell, e.g.

```py
import time
time.sleep(3)
"hello"
```

and press _Shift_ + _Enter_

## Writing and evaluating code

IPython has numbered inputs, e.g. `In [1]`

When a computation is ongoing it will display `In [*]`

If the last statement in a cell evaluates to something it will be considered the output and displayed

In order to restart the notebook and re-evaluate all cells, press ⏩

## Accessing the last output

```py
print(_ * 3)
```

## Writing documentation via markdown

We can add documentation via the standardized _markdown_ language:

Change the dropdown from _Code_ to _Markdown_ and try the following code:

```md
# Heading

- item 1
- item 2
```

Run the cell to display the result, double click to edit again

[markdown cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)

## Documentation

displaying documentation in any Python console:

```py
help(str)
```

(navigate through long outputs via _Enter_, exit via _Q_)

shortcut for IPython / Jupyter:

```ipython
str?
```

## Tab completion and wildcard expressions

```ipython
*Error?
```

## Running terminal commands

IPython includes direct access to many terminal commands, e.g. `ls`, `cd`, ...

We can execute any terminal command by prefixing it with `!`

# NumPy

## NumPy

Library for efficient data processing

Data are stored in multidimensional arrays of numeric values which are implemented in an efficient way

Data can represent images, sound, measurements and much more

## NumPy

common import convention:

```python
import numpy as np
```

## NumPy

NumPy Arrays vs Python lists:

Arrays are implemented in C; the entries (e.g. integers) are not Python Objects and are therefore lighter on resources

## NumPy

NumPy Arrays vs Python lists:

```py
# Python lists (with references to Python integer objects)
list_a = [1, 2]
list_b = [3, 4]

# NumPy array
# data are contained within the array without referencing
# Python integers
array_a = numpy.array(list_a)
array_b = numpy.array(list_b)

# fast multiplication (implemented in C)
array_a * array_b
```

## Arrays

Each array can only hold data of one type (e.g. only 64 bit floats or only bytes)

## Arrays

Creating a 2-dimensional array:

```py
np.array([[1, 2, 3], [2, 4, 6], [3, 6, 9]])
```

output:

```py
array([[1, 2, 3],
       [2, 4, 6],
       [3, 6, 9]])
```

## Arrays

Creating a 3-dimensional array:

```py
np.array([[[1, 2], [3, 4]], [[5, 6], [7,8]]])
```

output:

```py
array([[[1, 2],
        [3, 4]],

       [[5, 6],
        [7, 8]]])
```

## Array types

Each array has a predefined data type for all entries

```py
a = np.array([1])
a.dtype # int32
b = np.array([1.0])
b.dtype # float64
c = np.array(['abc'])
c.dtype # <U3
d = np.array([b'abc'])
d.dtype # |S3
```

## Array types

Types may be stated explicitly:

```py
a = np.array([1], dtype='int64')
b = np.array([1], dtype='uint8')
```

If possible, types are converted automatically:

```py
c = a + b
c.dtype # int64
```

## Array types

common types:

- _bool_ / <em>bool\_</em> (stored as 8 bits)
- _int8_, _int16_, _int32_, _int64_
- _uint8_, _uint16_, _uint32_, _uint64_
- _float16_, _float32_, _float64_

## Overflow

Be careful with values that are too big or too small

The type `int8` is only suitable for values in the range from `-128` to `+127`

```py
np.array([127, 128, 129], dtype="int8")
```

Output:

```py
array([127, -128, -127])
```

## Operations on arrays

operations are applied element-wise:

```py
a = np.array([1, 2, 3])
b = np.array([2, 2, 2])

print(a + b)
# np.array([3, 4, 5])
print(a * b)
# np.array([2, 4, 6])
```

## Exercises

given an array of prices and an array of quantities, determine the total price:

```py
prices = np.array([3.99, 4.99, 3.99, 12.99])
# buying the first item 3 times and the last item 2 times
quantities = np.array([3, 0, 0, 2])

# solution: 37.95
```

given the coordinates of the vertices of a triangle (in 2D or 3D), determine its centroid

```py
a = np.array([5, 1])
b = np.array([6, 8])
c = np.array([1, 3])

# solution: [4, 4]
```

## Exercises

advanced:

- solving linear equations

# Pandas

## Pandas

_Pandas_ is a data analysis library; it is based on _NumPy_

```py
import pandas as pd
```

## Series and DataFrame

- **Series**: Collection of values for some keys (table column)
- **DataFrame**: Collection of associated series (table)

Example:

|     | Area | Population | Capital          |
| --- | ---: | ---------: | ---------------- |
| CN  |  9.6 |       1386 | Beijing          |
| RU  |   17 |        144 | Moscow           |
| US  |  9.8 |        327 | Washington, D.C. |

## Series

```py
area = pd.Series({'CN': 9.6, 'RU': 17, 'US': 9.8})
population = pd.Series({'CN': 1386, 'RU': 144, 'US': 327})
capital = pd.Series({'CN': 'Beijing', 'RU': 'Moscow',
                     'US': 'Washington, D.C.'})

area[0] # 9.6

area['CN'] # 9.6
```

## Series

Each series has a specific data type

```py
area.dtype # float64
```

Manually setting the datatype:

```py
area = pd.Series({"CN": 9.6, "RU": 17, "US": 9.8},
                 dtype="float32")
```

## DataFrame

```py
countries = pd.DataFrame({
    'area': area,
    'population': population})
```

# Reading CSV

## Reading CSV

Example: Euribor (interest rates of European bonds)

```py
euribor = pd.read_csv(
    "https://datahub.io/core/euribor/r/euribor-12m-monthly.csv",
    index_col="date")
```

Example: Iris Dataset

```py
iris = pd.read_csv(
    "http://archive.ics.uci.edu/ml/machine-learning-databases/iris/iris.data",
    header=None,
    names=["sepal_length", "sepal_width", "petal_length",
           "petal_width", "name"],
)
```

## Reading CSV

Example: S&P 500 monthly prices

```py
sp500 = pd.read_csv(
    "https://datahub.io/core/s-and-p-500/r/data.csv",
    index_col="Date")
```

Example: exchange rates

```py
exchange_rates = pd.read_csv(
    "https://datahub.io/core/us-euro-foreign-exchange-rate/r/monthly.csv",
    parse_dates=[1])
```

# Pandas: Querying data

## Querying data (by row numbers / column numbers)

- `df.iloc[5]`: row 5 (returns a `Series` object)
- `df.iloc[:5]`: first 5 rows (returns a `DataFrame` object)
- `df.iloc[10:20]`: rows 10-19
- `df.iloc[5, 1]`: row 5, column 1
- `df.iloc[5, [0, 2]]`: row 5, column 0 and 2

## Querying data (by row names / column names)

- `df.index`: row names
- `df.columns`: column names

<!-- -->

- `df.loc["2009-01-02"]`: Row by index value
- `df.loc["2009-01-01":"2009-01-31"]`: Row in a specified range (both values included)
- `df.loc[:, "rate"]`: column `"rate"`
- `df["rate"]`: column `"rate"` (short version)
- `df.rate`: column `"rate"` (extra short version - only works with no special characters)
- `df.loc[:, ["rate", "maturity_level"]]`: two columns
- `df.loc["2009-01-02", "rate"]`: specific row and column

## Filtering rows

via _boolean indexing_:

- `df.loc[df.rate < 0]`
- `df.loc[df.name == "Iris-setosa"]`
- `df.loc[df.name.isin(["Iris-setosa", "Iris-virginica"])])]`

## Sorting rows

- `df.sort_index(ascending=False)`
- `df.sort_values(by="rate")`
- `df.loc["2009-01-02" : "2009-12-31"].sort_values(by="rate")`

## Exercises (Euribor)

- first entry
- last entry
- last 10 entries
- entry from 2009-01-02
- entries from the year 2009
- ...

## Solutions (Euribor)

- first entry: `euribor.iloc[0]`
- last entry: `euribor.iloc[-1]`
- last 10 entries: `euribor.iloc[-10:]`
- entry from 2009-01-02: `euribor.loc["2009-01-02"]`
- entries from the year 2009: `euribor.loc["2009-01-01": "2009-12-31"]`

## Exercises (Iris)

- maximum _petal length_ of _iris setosa_ (without using `.max`)

# Data statistics

## Data statistics

```py
df.describe()
```

## Statistics on a data frames / series

```py
countries.area.describe()
```

```txt
count     3.000000
mean     12.133333
std       4.215843
min       9.600000
25%       9.700000
50%       9.800000
75%      13.400000
max      17.000000
dtype: float64
```

(see next slide for explanations)

## Statistics on series

```py
countries.area.describe()
```

The above computes the following data:

- `area.count()`
- `area.mean()`
- `area.std()`
- `area.quantile(0)` / `area.min()`
- `area.quantile(0.25)`
- `area.quantile(0.5)` / `area.median()`
- `area.quantile(0.75)`
- `area.quantile(1)` / `ara.max()`

## Statistical quantities

- _std_: _Standard deviation_
- _median_: half of the values are less and half are greater than the median
- _min_: all values are greater than the minimum
- _25%-quantile_: 25% of all values are less

# Example: exchange rates

## Exchange rates

https://datahub.io/core/exchange-rates/r/daily.csv

Daily Exchange rates between USD and other countries

We will read exchange data - transform it so it only contains data for EUR-USD exchange rates and turn the dates into the index

## Exchange rates

Solution:

```py
er = pd.read_csv(
    "https://datahub.io/core/exchange-rates/r/daily.csv",
    parse_dates=[1])

# only select euro
er_eur_full = er.loc[er.Country=="Euro"]

# now we can set the date as the index
er_eur_dateindex = er_eur_full.set_index('Date')

# we can drop the country information
er_eur = er_eur_dateindex.loc[:, 'Value']
```

# Pandas: setting data

## Computing derived data

Adding a new column:

```py
iris["sepal_ratio"] = iris["sepal_length"] / iris["sepal_width"]

iris["sepal_ratio"].mean()
iris["sepal_ratio"].std()

iris_setosa = iris.loc[
    iris["name"] == "Iris-setosa"
]

iris_setosa["sepal_ratio"].mean()
iris_setosa["sepal_ratio"].std()
```

## Computing derived data via NumPy

Task:

- Analyze the S&P 500 monthly data and determine the monthly gain / loss in percent for each month
- What was the biggest loss / gain in a month?

## Computing derived data via NumPy

converting to NumPy array:

```py
values_np = sp500["SP500"].to_numpy()
```

differences of sequential months:

```py
diffs = values_np[1:] - values_np[:-1]
# add a single NaN to the front
diffs = np.concatenate([
    np.array([float('nan')]), diffs])
```

adding to pandas data:

```py
sp500["Diff"] = diffs
sp500["Gain"] = sp500["Diff"] / sp500["SP500"]
```

## Setting data

```py
iris.iloc[0, 0] = 6

iris.loc[:, "sepal_ratio"] = float('nan')
```

# Importing and exporting data

## Importing and exporting data

data formats:

- CSV
- Excel
- JSON
- HDF5 (efficient binary format)
- SQL tables (via _SQLAlchemy_)

## Importing and exporting data

import: `pd.read_csv`, `pd.read_excel`, ...

export: `df.to_csv`, `df.to_excel`, ...

## Importing and exporting data

```py
df.to_excel('iris.xlsx')
```

```py
data = pd.read_excel('iris.xlsx', index_col=0)
```

## Importing and exporting data

HDF5:

- via _pytables_ (must me installed)

```py
df.to_hdf('data.hdf5', 'iris')
```

```py
pd.read_hdf('data.hdf5', 'iris')
```

# Missing data

## Missing data

In the exchange rate data there are some missing entries:

- some days are not present (weekends)
- some days are stored as `NaN`s

## Missing data

removing any rows with missing data:

```py
er = er.dropna()
```

filling any rows with missing data with zeros:

```py
er = er.fillna(0)
```

filling any missing data with the value from the previous row:

```py
er = er.fillna(method="backfill")
```

## Missing data

interpolating data:

```py
er = er.intepolate()
er = er.interpolate(method="spline")
```

interpolating example:

```py
url = 'https://datahub.io/core/interest-rates-gb/r/data.csv'

ir_uk = pd.read_csv(url, index_col="date",
                    parse_dates=True)

ir_uk_weekly = ir_uk.resample('7d').interpolate()
```

# Plotting

## Plotting

general procedure:

In Jupyter:

```py
data_frame.plot()
```

In the terminal:

```py
import matplotlib.pyplot as plt

data_frame.plot()

# show all figures that were created since the last
# call to .show()
plt.show()
```

## Plotting functions

```py
# graph
data.plot()
# bar chart
data.plot.bar()
# box plots
data.plot.box()
# histograms
data.plot.hist()
# scatter plots
data.plot.scatter(x="colname_1", y="colname_2")
# scatter matrix
from pandas.plotting import scatter_matrix
scatter_matrix(data)
```

## Graphs

example:

```py
euribor.plot()
sp500["SP500"].plot()
```

## Bar charts

example:

```py
euribor.iloc[-36:].plot.bar()
```

exercise:

plot median _sepal-width_ and _sepal-length_ for all three types of flowers

## Box plots

Display statistical data in a diagram (min, median, max, ...)

```py
iris.plot.box()
```

## Histograms

counts occurrences of certain values / value ranges

examples:

```py
iris.sepal_lenght.plot.hist()
```

```py
iris.sepal_length.plot.hist(bins=30)
```

## Histograms

exercise:

simulate 10 million rolls of dice - each using 10 dice; plot the distribution of the sums as a histogram

## Scatter plots

creates data points with two values - one on the x-axis and the other on the y-axis

```py
iris.plot.scatter(x="sepal_length", y="sepal_width")
```

task: scatter plot of just _Iris-setosa_

## Scatter matrix

creates several scatter plots - if there are 4 data series it will create 4x4 plots (scatter plots and histograms)

```py
from pandas.plotting import scatter_matrix

scatter_matrix(iris)
```

# NumPy advanced

## Creating arrays

create a 2x6 array filled with 0.0:

```py
np.full((2, 6), 0.0)
```

create the sequence _0.0, 0.5, 1.0, 1.5_:

```py
# fixed step width (0.5)
a = np.arange(0, 2, 0.5)
# fixed number of entries (4)
b = np.linspace(0, 1.5, 4)
```

create a 3x3 array of random values:

```py
np.random.random(3, 3)
```
